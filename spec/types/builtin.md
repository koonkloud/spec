# Built-in Datatypes

These are the built-in datatypes that are essential for the rest of the KB to be built apon.

_**⚠️ NOTE**_: All built-in datatypes use the notation of lowercase names

## Atomic

These are the base types.

### string

A string, not to be confused with **Text**, is the same for any language.

For the context of this program, it is important to understand how a **string** is used, versus how **Text** is used.

```yaml
foo: bar
# is equal to:
foo:
    $type: Text
    equals: bar
```

In both cases, `foo` is strictly equal to `"bar"`. In the second case, a string is used for the `equals` field.

The difference is more noticeable in this example:

```yaml
foo:
    $type: Text
    startsWith: b
```

The **string** type is only used with the `startsWith` field to create the **Text** object. Hopefully this illustrates the difference between the two.

### number

Because we are using Node as our runtime, there is no need to differentiate between Integers, Floats, and other number formats at a core level.

Just as the `Text` type allows for specific strings to be targetted, the `Number` type has attributes to specify certain numbers.

For example, the Integer type is defined as:

```yaml
Integer:
    $type: Number
    isWhole: true
```

The `Number` object, has the `val` attribute, which is where the actual value of the number is stored, which has a type of `number`.

This means that no matter if it's a `Number` or `Integer`, the `val` always has a `number`. The difference is that `Integer` will do a type check when it's instantiated.

### boolean

A `true` or `false` value.

There is no need for a `Boolean` type at the moment.

### null

A `null` value.

_**⚠️ NOTE**_: All `undefined` values should be cast to `null`.

## Non-atomic Types

### list

A list, in other languages, called an array, is a collection of other types. The built-in type contains no type information.

The `List` type allows for type, size, and duplicates specifications.

### object

_**⚠️ NOTE**_: The keys of an object will always be `string`s.
