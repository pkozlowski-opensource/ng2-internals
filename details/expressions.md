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

### Binding expressions

### Template binding expressions

### Interpolation expressions

## Comparing with JavaScript expressions

# Parsing and lexing

[Parser](https://github.com/angular/angular/blob/ec5cb3eb66aa343bbc7f67c182c1cc021ce04096/modules/change_detection/src/parser/parser.js#L35-L82)

[Lexer](https://github.com/angular/angular/blob/master/modules/change_detection/src/parser/lexer.js)


