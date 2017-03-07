# Javascript Properties

```Javascript
var cat = {
    name: 'fluffy',
    color: 'white'
}

Object.getOwnPropertyDescriptor(cat, 'name')

{
    value: fluffy,
    writeable: true,
    enumerable: true,
    configurable: true
}

Object.defineProperty(cat, name, {writeable: false})

{
    {
        value: fluffy,
        writeable: false,
        enumerable: true,
        configurable: true
    }
}
```
## Writeable
**Changing writeable to false doesn't completely stop editing of the name value, following is a work around**
```Javascript
var cat = {
    name: {first: 'fluffy', last: 'diva'},
    color: 'white'
}

Object.defineProperty(cat, name, {writeable: false});
console.log(cat.name.first) -> 'fluffy' 
```

**To completely Freeze name use the following**
```Javascript
Object.Freeze(cat.name);
console.log(cat.name.first);    ->  TypeError!
```

## Enumerable 
**Set Properties visible during looping through object**
```Javascript
var cat = {
    name: 'fluffy',
    color: 'white'
}
Object.defineProperty(cat, 'name', {enumerable: false})

for(var val in cat){console.log(val)} -> color
```

## Configurable
**Locks down a property from certain attributes being changed**
```Javascript
var cat = {
    name: 'fluffy',
    color: 'white'
}
Object.defineProperty(cat, 'name', {configurable: false})

cannot change enumerable or configurable or delete the property
You can however change writeable.
```