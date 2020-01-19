# Array Methods in JavaScript

## Helpful Array manipulating

### Remove Duplicates from an Array

There are multiple ways to remove duplicates from an array in JS.

One simple approach is to use the <strong>Set</strong> object. The <strong>Set</strong> object lets you store unique values, of any type. <strong>Set</strong> will automatically remove duplicates for us.

``` 
const names = ['John', 'Paul', 'George', 'Ringo', 'John'];

let unique = [...new Set(names)];
```

