---
title: "Mocks"
description: "" 
date: 2022-09-28T19:22:43
tags: [""]
categories: [""]
draft: false
---
Los mocks son maneras de creear funciones falsas, que contengan dummy code, que simulen actuar y retornar valores que nuestras funciones necesitan, funciones de otros modulos.

El objeto de testear la aplicacion no es comprobar si por ejemplo nuestra funcion, crea o no un arhivo, es comprobar como se comporta si le pasamos determinados valores o verificar que retorna.

Por eso si en nuestra funcion usamos, funciones d enode como readFile, es mejor crear nuestra propia vercion de esa funcion, que retorne lo que esa funcion retornaria, y simular que se esta ejecutando, asi evitar que se ejecute y cree un archivo donde no deberia o que haga una accion que no deberia.

## implemetancion

Las simulaciones mock manuales son usadas para sustituir funcionalidad con datos falsos. Por ejemplo, en lugar de acceder a un recurso remoto como un sitio web o una base de datos, puede que se desee crear una simulación manual que permita usar datos falsos. Esto asegura que las pruebas serán rápidas y estables.

Las simulaciones mock manuales se definen escribiendo un modulo en el subdirectorio **mocks** el cual se debe encontrar adyacente al módulo. Por ejemplo, para simular un módulo llamado user en el directorio models, se debe crear un archivo [user.sj](http://user.sj/) y colocarse en el directorio models/**mocks**. Si el directorio que se esta sustituyendo es un modulo de node (por ejemplo fs), el mock debe colocarse en el directorio **mocks** adyacente al directorio node_modules. Por ejemplo:

```
├── config
├── __mocks__
│   └── fs.js
├── models
│   ├── __mocks__
│   │   └── user.js
│   └── user.js
├── node_modules
└── views
```

Cuando una simulación mock manual existe para un módulo, el sistema de módulos de Jest usará dicho mock cuando se llame a la función jest.mock('nombreModulo'). Sin embargo, para módulos de node, el mock será usado aunque no se llame a la función jest.mock('nombreModulo'). Para omitir este comportamiento, se debe llamar de manera explicita a jest.umock('nombreModulo') en pruebas donde se desee usar la implementación real del módulo.

A continuación se muestra un ejemplo inventado de un módulo que provee un resumen de todos los archivos de un directorio.

```
// FileSummarizer.js
'use strict';

const fs = require('fs');

function summarizeFilesInDirectorySync(directory) {
  return fs.readdirSync(directory).map(fileName => ({
    directory,
    fileName,
  }));
}

exports.summarizeFilesInDirectorySync = summarizeFilesInDirectorySync;
```

Como es deseable que las pruebas eviten depender del disco (que es lento y frágil), se puede crear un mock manual para fs extendiendo el mock automático. El siguiente mock implementa versiones personalizadas del API de fs que puede ser usada en las pruebas:

```
// __mocks__/fs.js
'use strict';

const path = require('path');

const fs = jest.genMockFromModule('fs');

// This is a custom function that our tests can use during setup to specify
// what the files on the "mock" filesystem should look like when any of the
// `fs` APIs are used.
let mockFiles = Object.create(null);
function __setMockFiles(newMockFiles) {
  mockFiles = Object.create(null);
  for (const file in newMockFiles) {
    const dir = path.dirname(file);

    if (!mockFiles[dir]) {
      mockFiles[dir] = [];
    }
    mockFiles[dir].push(path.basename(file));
  }
}

// A custom version of `readdirSync` that reads from the special mocked out
// file list set via __setMockFiles
function readdirSync(directoryPath) {
  return mockFiles[directoryPath] || [];
}

fs.__setMockFiles = __setMockFiles;
fs.readdirSync = readdirSync;

module.exports = fs;
```

A continuación la prueba:

```
// __tests__/FileSummarizer-test.js
'use strict';

jest.mock('fs');

describe('listFilesInDirectorySync', () => {
  const MOCK_FILE_INFO = {
    '/path/to/file1.js': 'console.log("file1 contents");',
    '/path/to/file2.txt': 'file2 contents',
  };

  beforeEach(() => {
    // Set up some mocked out file info before each test
    require('fs').__setMockFiles(MOCK_FILE_INFO);
  });

  test('includes all files in the directory in the summary', () => {
    const FileSummarizer = require('../FileSummarizer');
    const fileSummary = FileSummarizer.summarizeFilesInDirectorySync(
      '/path/to'
    );

    expect(fileSummary.length).toBe(2);
  });
});
```

El ejemplo de mock mostrado aquí usa `[jest.genMockFrom Module](<https://deltice.github.io/jest/docs/jest-object.html#jestgenmockfrommodulemodulename>)`  para generar un mock automático, y reemplazar su comportamiento por defecto. Este es el enfoque recomendado, pero es completamente opcional. Si no se desea usar el mock automático, se puede simplemente exportar las funciones desde el archivo del mock. Una desventaja de los mocks completamente manuales es que realmente son manuales. Esto quiere decir que para actualizarlos manualmente cada vez que se modifica el módulo que reemplazan. Debido a esto, es mejor usar o extender el mock automático cuando se ajuste a las necesidades del proyecto.

Para garantizar que un mock manual y su implementación real se mantengan sincronizados, puede ser útil requerir el modulo real a través de require.requireActual(nombreModulo) en el mock manual y modificarlo con las funciones mock antes de exportarlo.
