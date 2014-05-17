---
layout: default
title: Basilisk - Values for Javascript
---

Struct
------

The simplest part of Basilisk is the idea of a **struct** - a record 
containing values at named positions.  For example 

```javascript
var Person = basilisk.makeStruct(['name', 'age', 'address']),
    Address = basilisk.makeStruct(['line1', 'line2', 'country', 'code']),
    joe;
    
joe = new Person({
    name: 'Joe Bloggs',
    age: 32,
    address: new Address({
        line1: '64 Tremaine Road',
        line2: 'London',
        country: 'United Kingdom',
        code: 'SE20 8AB'
    })
});
```

This gives you two types of structs: ``Person`` and ``Address``.  So far, so easy.
 
The key idea with structs is **how you get new structs from old**.

```javascript
var changedJoe = joe.with_('age', 35);
```

