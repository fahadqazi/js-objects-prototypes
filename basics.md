# Javascript Objects & Prototypes

### Simple Object creation
```Javascript
var car = {
    name: 'fluffy',
    color: white,
    speak: function(){console.log('meoow')}
}
```

### If you want to create multiple instance of an Object

__Constructor Function__
```Javascript
function Cat(name, color){
    this.name = name,
    this.color = color
}

var cat = new Cat('fluffy', 'white');
console.log(cat);
```

### ES6 Classes

```Javascript
class Cat {
    constructor (name, color){
        this.name = name;
        this.color = color;
    }
    speak(){
        console.log('meow');
    }
}

var cat = new Cat('fluffy', 'white');
console.log(cat);
cat.speak();
```