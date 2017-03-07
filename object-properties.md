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

**Changing writeable to false doesn't completely stop editing of the name value, following is a work around**
