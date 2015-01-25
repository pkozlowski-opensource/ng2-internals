# AngularJS expressions

A typical AngularJS template will be littered with different expressions present in HTML text nodes or attributes. For example:

```html
<template>
    <div>
        There are {{items.length}} items in the collection:
        <ul>
            <li template="ng-repeat: #item in items">{{item}}</li>
        </ul>
        <button on-click="clear()">Clear all</button>
    <div>
</template>
```

Even in a simple template like this we can identify a number of expressions:
* `items.length`
* `item`
* `ng-repeat: #item in items`
* `clear()`

Most of the identified expressions are identical to JavaScript ones: `items.length`, `item`, `clear()` but they meaning in a template is different. While `items.length` and `item` are here to display data, `clear()` represents an action (executed in response to a DOM event) that can have side effects. Oh, and `ng-repeat: #item in items` looks altogether different. All those differences in syntax and semantics suggest that there are several types of expressions.

## Different types of expressions

Angular2 template can contain 4 different types of expressions that are parsed and executed according to (slightly) different rules:
* **action** - ex.: `clear()`
* **binding** - ex.: `items.length`, `item`
* **template binding** - ex.: `ng-repeat: #item in items`
* **interpolation** - ex.: `There are {{items.length}} items in the collection:`

### Action expressions

* no filters (`|`)
* assignments
* multi-statement
* contextual info (event)

### Binding expressions

* filters (`|`)
* no assignments
* no multi-statement

### Template binding expressions

`ng-repeat: #item in items` is decomposed into pairs of `[keyword, expression]`, where:
 * `keyword` - a string
 * `expression` - a binding expression

### Interpolation expressions

Interpolation expressions are nothing more than text fragments mixed with expression expressions wrapped in `{{expr}}`.

- what is the output of parsing?

## Comparing with JavaScript expressions

# Parsing and lexing

## Parser

In Angular2 a [Parser](https://github.com/angular/angular/blob/master/modules/change_detection/src/parser/parser.js#2) is a class with the following interface:

 ```javascript
class Parser {

  parseAction(input:string, location:any):ASTWithSource {
   ...
  }

  parseBinding(input:string, location:any):ASTWithSource {
    ...
  }

  parseTemplateBindings(input:string, location:any):List<TemplateBinding> {
    ...
  }

  parseInterpolation(input:string, location:any):ASTWithSource {
   ...
  }
}
```

Each method accepts the same set of 2 arguments:
* `input` - expression (as string) to be parsed
* `location` - an arbitrary location pointing to a source of an expression being parsed (mostly for debugging purposes)

Most of the methods return an instance of the `ASTWithSource` interface which encapsulates [AST](http://en.wikipedia.org/wiki/Abstract_syntax_tree) of the parsed expression plus methods that can be used to evaluate the expression (see below).

## Lexer

[Lexer](https://github.com/angular/angular/blob/master/modules/change_detection/src/parser/lexer.js)
- types of tokens
- structure of a given token


# Evaluating expressions