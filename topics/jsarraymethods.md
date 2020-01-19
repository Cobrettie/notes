# Array Methods in JavaScript

## Helpful Array Information

- Arrays are mutable, can add items, delete items, etc.
- Arrays are still an object, with different behavior
- Arrays are just a special type of object
  - The ability to store ordered values makes arrays special
  - Arrays are treated with a key:value pairing system
  - Arrays have 0 based indexing 
  ``` testArray = ['item1', item2', 'item3'];
      console.log(testArray[0]); // will log item1
      console.log(testArray[1]); // will log item2
  ```
- You can access any item inside of an array
  - select the array
  - use bracket notation to choose which index you want
  ``` console.log(testArray[2]) // will log item3 ```

## Popular Array Methods

- .push() adds an item to the end of an array

``` 
testArray.push('test item');
// adds 'test item' to the end of testArray
```

- unshift() adds an item to the front of an array

```
testArray.unshift('test item');
// adds 'test item' to the front of testArray
```

- .pop() removes the last item from an array

```
testArray.pop();
// will remove the last item from testArray
```

- .shift() removes the first item from an array

``` 
testArray.shift();
// will remove the first item from testArray
```

- .splice() removes a specific item from an array

```
testArray.splice();
// will remove an item at the specified index that is passed into .splice()
```

## Some Advanced Array Methods

- .map()
- .reduce()
- .filter()

## Helpful Array Manipulating

### Remove Duplicates from an Array

There are multiple ways to remove duplicates from an array in JS.

One simple approach is to use the <strong>Set</strong> object. The <strong>Set</strong> object lets you store unique values, of any type. <strong>Set</strong> will automatically remove duplicates for us.

``` 
const names = ['John', 'Paul', 'George', 'Ringo', 'John'];

let unique = [...new Set(names)];
```
