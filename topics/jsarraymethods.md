# Array Methods in JavaScript

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

## Helpful Array Manipulating

### Remove Duplicates from an Array

There are multiple ways to remove duplicates from an array in JS.

One simple approach is to use the <strong>Set</strong> object. The <strong>Set</strong> object lets you store unique values, of any type. <strong>Set</strong> will automatically remove duplicates for us.

``` 
const names = ['John', 'Paul', 'George', 'Ringo', 'John'];

let unique = [...new Set(names)];
```
