# Types System

## Goals

1. Ground-up type declaration
2. Semi-structured schema based objects

### Ground-Up Type Declaration

Besides the built-in types, every type should be able to be declared and stored in the knowledge base.

To illistrate how this is supposed to work, we will try to define the `Text` and `Letter` types.

```yaml
Text:
    $type: object
    equals:
        $type: string
    startsWith:
        $type: string
    endsWith:
        $type: string
    size:
        $type: number
```

For the character type.

```yaml
Character:
    $type: Text
    size: 1
```
