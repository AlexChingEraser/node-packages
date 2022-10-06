# Joi
data validation in js

## How to Use?
```javascript
const Joi = require('joi');

const schema = Joi.object({
    username: Joi.string()
        .alphanum()
        .min(3)
        .max(30)
        .required(),
})
schema.validate({ username: 'abc', birth_year: 1994 });
const value = await schema.validateAsync({ username: 'abc', birth_year: 1994 });
```

take `username` as example: we should define the **rules** as the argument:
- a **required** string
- must contain only alphanumeric characters
- at least 3 characters long but no more than 30
- must be accompanied by birth_year

## Functions
1. closure interfaces
```javascript
const Joi = require('joi');
const { object, string } = Joi.types();

const schema = object.keys({
    property: string.min(4)
})
```

2. types
- `any()`
- `boolean()`
- `array()`
- `object()`