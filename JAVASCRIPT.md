Javascript Style Requirements
================

The goal of a styleguide/lint guide for code is to create code that is:

* Compact - Code libraries should be compact, logic should be bundled together and not spread out over many lines. 
* Easy to Read - Code should be easy to read and clearly documented when necessary.
* Not Burdensome to Write

In general, we follow the [JSLint Style Guide](http://www.jslint.com/help.html) and most of the [AirBnB style Guide](https://github.com/airbnb/javascript). With a few modifications and emphasis:
* We use 2 spaces for indentations instead of 4 spaces.
* **NO TABS EVER**

Pull requests that do not meet this linting/style guide **will be rejected**.


Semi-Colons
===================
Semi-colons are no longer required in Javascript. Please do not use them unless required to fix some particular bug.



Arrays
===================
Use literals for defining arrays:

```js
const items = []
```


Variables
==================
Properly scoping variables is important. Please stick to using `let` and `const` and only using `var` when absolutely necessary. Just a reminder from the JS docs:

* The let statement, which is like the var statement except that it respects block scope. You may use let or var but not both.
* The const statement is like the let statement except that it disallows the use of assignment on the variable, although if the value of the variable is mutable, it can still be mutated. const is preferred to let.


```js
// yes
const x = 'a'
let y = 'b'

// no
var z = 'c'
```

Promises
=====================
Promises have a tendency to get pretty ugly in javascript. We prefer the below formatting example.

```js
whenSomethingHappens()
  .then(whenSomethingElse)
  .catch(console.log)
  .finally(() => console.log("finally"))
```

In the case of multiple lines, we prefer the following ES6-like formulation. Below is an example using fetch:

```js
fetch('http://checkip.dyndns.org/')
  .then(response => response.json())
  .then(json_resp => console.log(json_resp))
  .catch(error => console.error(error))
```
If you need a multiline promise reponse, see the example below. Wrap in a `{}` block
```js
fetch('http://checkip.dyndns.org/')
  .then(response => response.json())
  .then(json_resp => {
    console.log("this is a multi line.")
    console.log(json_resp)
  })
  .catch(error => console.error(error))
```


React Components
===================
There are websites with [https://css-tricks.com/react-code-style-guide/](Some Good React Style Suggestions). We recommend these.

For the love of god, please break down your React Components into smaller reusable components. Something is wrong if your react component is basically a bunch of HTML - think thru each individual component and try to break it into as small of piece as possible. For example:

```js
// bad
render() {
  return (<div>
    <div>{this.props.name}</div>
    <div>{this.props.address1} {this.props.address2}<div>
  </div>)
}

// good
render() {
  return (<div>
    <div>{this.props.name}</div>
    <div><AddressBlock line1={this.props.address1} line2={this.props.address2} /></div>
  </div>)
}
```

This is clearly more of an art than a science and requires some practice. However, you should seek to break down components into the smallest re-usable components possible.


Lining Up Enclosures
====================
Enclosures should be lined up so the closing bracket is clearly aligned with the opening of the enclosure above. For example:


```js
// bad
return (<div>
 <span>
 </div>)

// good
return (
  <div>
    <span/> 
  </div>
)
```
