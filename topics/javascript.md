# JavaScript

## Variables in JavaScript

### var
- function scoped, meaning the variable is only available inside of the function they are created in, unless the variable is declared globally.
- hoisted
- can be reassigned or overridden i.e redefined or updated

- Example of variable scope
![Variable Scope in JavaScript](../js-images/variable-scoping.png)

### let
- block scoped
- not hoisted
- can be reassigned, but NOT overridden

### const
- block scoped
- not hoisted
- immutable, cannot be reassigned or overridden
- the most strict of all variable keywords in JS, meaning it has the most rules applied 