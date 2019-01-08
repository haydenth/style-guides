Javascript Style Requirements
================

The goal of a styleguide/lint guide for code is to create code that is:

* Compact - Code libraries should be compact, logic should be bundled together and not spread out over many lines. 
* Easy to Read - Code should be easy to read and clearly documented when necessary.
* Not Burdensome to Write

In general, we follow the [JSLint Style Guide](http://www.jslint.com/help.html). With a few modifications and emphasis:
* We use 2 spaces for indentations instead of 4 spaces.
* **NO TABS EVER**


Promises
=====================
Promises have a tendency to get pretty ugly in javascript. We prefer the below formatting example.

```js
whenSomethingHappens()
  .then(whenSomethingElse)
  .catch(console.log)
  .finally( () => console.log("finally"))
```

In the case of multiple lines, we prefer the following ES6-like formulation:

```js
whenSomethingHappens()
  .then(() => return whenSomethingElse)
  .catch(console.log)
  .finally( () => console.log("finally"))
```

