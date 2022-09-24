---
title: "better-docs"
date: 2022-09-08T16:46:21
tags: [""]
categories: [""]
draft: false
---

# Better Docs

## @category plugin

### usage

```javascript
...
"tags": {
    "allowUnknownTags": ["category"] //or true
},
"plugins": [
    "node_modules/better-docs/category"
],
...
```

```javascript
/**
 * Class description
 * @category Category
 * @subcategory All
 */
class YourClass {
  ....
}
```

## @component plugin

### Installation instructions

```javascript
...
"tags": {
    "allowUnknownTags": ["component"] //or true
},
"plugins": [
    "node_modules/better-docs/component"
],
...
```

```javascript
# if you use npm
npm install -g parcel-bundler

# or yarn
yarn global add parcel-bundler
```

### Usage

```javascript
/**
 * Some documented component
 *
 * @component
 */
const Documented = (props) => {
  const { text } = props
  return (
    <div>{text}</div>
  )
}

Documented.propTypes = {
  /**
   * Text is a text
   */
  text: PropTypes.string.isRequired,
}

export default Documented
```

### Preview

```javascript
/**
 * Some documented component
 *
 * @component
 * @example
 * const text = 'some example text'
 * return (
 *   <Documented text={text} />
 * )
 */
const Documented = (props) => {
  ///...
}
```

You can put as many @example.  
tags as you like in one component and "caption" each of them like this:

```javascript
/**
 * @component
 * @example <caption>Example usage of method1.</caption>
 * // your example here
 */
```

### Mixing components in preview

```javascript
// component-1.js
/**
 * Component 1
 * @component
 *
 */
const Component1 = (props) => {...}

// component-2.js
/**
 * Component 2
 * @component
 * @example
 * return (
 *   <Component1>
 *     <Component2 prop1={'some value'}/>
 *     <Component2 prop1={'some other value'}/>
 *   </Component1>
 * )
 */
const Component2 = (props) => {...}
```
