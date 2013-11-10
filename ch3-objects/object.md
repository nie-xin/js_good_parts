Objects
---

Objects are mutable keyed collections.

###object literals

An object literal is a pair of curly braces surrouding zero or more name/value pairs.

    var empty_object = {};

    // object literal example
    // the quotes are optional if the name would be a legal js name and not a reserved word
    // so quotes are required for first-nanme but optional for first_name
    var stoog = {
        "first-name": "nie",
        "last-name": "Howard"
    };

###retrieval values

1. [] suffix

    stoog["first-name"]

2. dot(.) could be used if it's legal js name and not a reserved word
    flight.departure.IATA

The dot notation is preferred.

###reference
Objects are passed by reference, they are never copied.

###prototype
Object is linked to a prototype object from which it can inherit properties. When you make a new object, you can select the object that should be its prototype. For simplify this mechanism, we could add a create method to the object function.

    if (typeof Object.create !== 'function') {
        Object.create = function (o) {
            var F = function() {};
            F.prototype = o;
            return new F();
        };
    }
    var another_stooge = Object.create(stooge);
    
    }