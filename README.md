# Javascript Decorators

Decorators are just functions that take in a piece of code, try to make it nicer and extend it (decorate it!), and return that extended piece of code. A higher order function if you will.

**Note**: Decorators are currently a stage 2 proposal which means they’re still not in JavaScript but probably will be in the future.

### What is the decorator pattern?
In object-oriented programming, the decorator pattern (also known as Wrapper, an alternative naming shared with the Adapter pattern) is a design pattern that allows behavior to be added to an individual object, either statically or dynamically, without affecting the behavior of other objects from the same class. The decorator pattern is often useful for adhering to the Single Responsibility Principle, as it allows functionality to be divided between classes with unique areas of concern.
Definition taken from Wikipedia. 

### So what does Python say decorators are?
A decorator is a function that takes another function and extends the behavior of the latter function without explicitly modifying it.
Definition taken from Primer on Python Decorators.

**Example 1:** Basic Example
```javascript
function hello(target) {
  target.prototype.hello = 'Hello';
  //we add it to the prototype, so every instance has access to the `bam` property
}

@hello
class welcome {
  world = 'World';
}

const sound = new welcome();
console.log(sound.hello); //Hello
console.log(sound.world); // World
```

**Example 2:** Decorators inside class
```javascript
function readonly(target, name, descriptor) {
  descriptor.writable = false;
  return descriptor;
}

class Example {
  a() {}
  @readonly
  b() {}
}

const e = new Example();
e.a = 1;
e.b = 2;
// TypeError: Cannot assign to read only property 'b' of object '#<Example>'
```

**Example 3:** Decorators with parameters 
```javascript

```
