# lodash

## Purpose
The description in `lodash` is `A modern JavaScript utility library delivering modularity, performance & extras.`, So the main purpose is `utility`. `lodash` provide dozens of method for different dimensions:
- Array: `[]`
- Collection: `[]`, `[[],[]...]`, `[{},{}..]`,...
- Seq: behave like `linq` operations for `Collection` or `Array`
- Date
- Function: create specific functions
- Lang: Provides classes that are fundamental to the design of the Javascript programming language
- Math
- Number
- Object: Object operation
- String
- Util
- Property
- Methods
  
Importantly, those lodash methods can be implement yourself, but lodash optimize those procedures and perform more efficiently.

If you don't like use it, just implement yourself, that's ok. maybe we can see source code and get hint~

## Porblem it Solved
utility tools collection for `Array`, `Collections`, `Functions`, `Object`, `String`,etc

## How lodash Use
The method that lodash provide can't display all in those tiny article, maybe the best way is read it in https://lodash.com/docs/4.17.15.

I mark some that is useful for me:

### Lang
- `isNan`,`isEmpty`,`isNil`,`isNull`.`isUndefined`
```javascript
//lodash/isUndefined.js
function isUndefined(value) {
  return value === undefined
}
```
- `clone`,`cloneDeep`
- `isEqual`: deep comparsion
- `isEmpty`: whether is an empty `object`, `collection`, `map` or `set`
```javascript
// .length or .size to judge
// not to check null, boolean, number,like:
_.isEmpty(null);
// => true
 
_.isEmpty(true);
// => true
 
_.isEmpty(1);
// => true
```
- `isSymbol`
- `isTypedArray`