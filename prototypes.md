# Prototypes

example
```javascript
var arr = [1,2,3,4,5];

Object.defineProperty(Array.prototype, 'last', {
    get: function(){
        return this[this.length-1]
    }

var last = arr.last    -> 5
})
```

**A function's prototype is the object instance that will become the prototype for all objects created using this function as a constructor**

**An object's prototype is the object instance from which the object is inherited**

example
```javascript
var Cat = function(name, color){
	this.name = name;
	this.color = color;
}

var fluffy = new Cat('fluffy', 'white');
var muffin = new Cat('muffin', 'black');
Cat.prototype === fluffy.__proto__ -> true

//change prototype for Cat function

Cat.prototype.age =3

console.log(fluffy.age) -> 3

//setting age for muffin
muffin.age = 5

//still have access to muffin's age from its prototype
console.log(muffin.__proto__.age); -> 3
```

## Class syntax for prototypal inheritance

```javascript

class Animal{
    constructor(voice){
        this.voice = voice || 'grunt';
    }
    speak(){
        console.log(this.voice)
    }
}

class Cat extends Animal {
    constructor(name, color){
        super('Meow');
        this.name = name;
        this.color = color
    }
}

```
