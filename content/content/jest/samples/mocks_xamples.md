---
title: "Mocks Xamples"
description: "" 
date: 2022-09-28T19:19:15
tags: [""]
categories: [""]
draft: false
---

# 1

```jsx
__mocks__/fs.js
const fs = jest.genMockFromModule('fs');
let __content;
function __readFileContent(content) {
    __content = content
}
function readFileSync(path,options) {
    return __content;
}

fs.readFileSync = readFileSync;
fs.__readFileContent = __readFileContent;
module.exports = fs;
```

```jsx
__test__/file.test.js
jest.mock('fs');
const {leer} = require('../vagina');
describe('test', () => {
    const content = '{"culo": 1}';
    const content2 = '{"culo": 2}';
    beforeEach(()=>{
        require('fs').__readFileContent(content);
    })
    test('truli', () => {
        expect(leer()).toEqual(content);
    });

});
```

# 2 Verificar si una funcion mock se esta llamado

```jsx
jest.mock('fs');
const fs = require('fs');
const {leer} = require('../vagina');
describe('test', () => {
    const content = '{"culo": 1}';
    const content2 = '{"culo": 2}';
    const mock = jest.spyOn(fs,'readFileSync');
    beforeEach(()=>{
        require('fs').__readFileContent(content);
    })
    test('truli', () => {
        expect(leer()).toEqual(content);
        expect(mock).toBeCalled();
    });

});
```
