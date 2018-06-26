![MongoDB Schema]()

## MongoDB Schema
___Using Mongoose, everything starts with a schema. A schema maps to a MongoDB document or collection and is a set of rules and instructions for creating models.___

At its core, a schema is like any other JavaScript object key-value pair. The key is the property name and the value is a Mongoose SchemaType. When a document is retrieved from the database, Mongoose attempts to convert the value to the related SchemaType and then return a model object.
- Can pass any field name/value pairs that we like
- There are also no rules on what values we can give to field names
- Document might not have all the fields that our application will require
- Schema is a set of rules for what property/value pairs a Document is allowed to take in order to be written to the database

The available SchemaTypes are:
- String 
- Number
- Date
- Buffer 
- Boolean 
- Mixed
- ObjectId 
- Array

It is also possible to declare custom SchemaTypes if the built-in ones fail to suit your needs.

#### Mixed Schema Type
Any value can be associated with a schema type listed as Mixed. This flexibility comes with a trade-off, however; it is difficult to maintain. Because Mongoose has no reliable way to compare changes to the value, the developer is responsible for alerting Mongoose any time the value changes. Using Mixed is best avoided, unless you’re really unsure what data is going to be used for the particular key.
 
#### Schema Example
```js
const userSchema = new mongoose.Schema({
  name: ‘String’,
  bio: ‘String’,
  emailAddresses: ‘Array’,
  address: {
    line1: ‘String’,
    city: ‘String’,
    postcode: ‘String’,
  }
});
```

#### Schema Validation Example
```js
const breakfastSchema = new Schema({
  eggs: {
    type: ‘Number’,
    min: [6, 'Too few eggs'],
    max: 12
}, bacon: {
    type: ‘Number’,
    required: [true, 'Why no bacon?']
  }
});
```

#### [Return: Express README](../../README.md)
