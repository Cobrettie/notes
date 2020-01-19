# Objects in JavaScript

## Helpful Object Literal Information

- Object Literal === literally an object in its simplest form

- An object is a collection of related data and/or functionality
- objects usually consist of variables and functions
  - the variables inside of objects are called <strong>properties</strong> 
  - the functions inside of objects are called <strong>Methods</strong>

Example of object properties
```
const testObject = {
  name: 'Your name here',
  age: 25,
  location: 'Anywhere',
  'favorite things': 'this, that, and the other are my favorite things';
}
// name, age, location, etc. are the properties
```

- Dot notation
  ``` console.log(testObject.name); ```

- Bracket notation
  ``` console.log(testObject['age']); // must use quotes when using bracket notation ```

  - Bracket notation is ideal when dealing with special characters
  ``` console.log(testObject['favorite things']); ```