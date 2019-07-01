---
id: Factory
title: Factory Design Pattern
sidebar_label: Factory Design Pattern
---

## About

A factory design pattern is another creational design pattern which which encapsulates object creation from the rest of the code. It can help instantiantite ad return different types of object based on complex logic and keep the codebase tidy.
An example can be different types of coffee. Based on an options object passed to the coffee factory method, it should return one of Expresso, Mocha or Latte.

## Code
```js

class Expresso {
    constructor(options){
        this.shots = options.shots ||3;
        this.sugar = options.sugar ||1;
        this.coffeeType =1;        
    }
}
class Mocha {
    constructor(options){
        this.shots = options.shots ||2;
        this.sugar = options.sugar ||3;
        this.coffeeType =2;        
    }
}

class Latte {
    constructor(options){
        this.shots = options.shots ||1;
        this.sugar = options.sugar ||4;
        this.coffeeType =3;        
    }
}

class CoffeeFactory {
    constructor(){   
    }
    getCoffee(options){
        if(options.type=="expresso")
            this.coffee = Expresso;
        else if(options.type=="mocha")
            this.coffee = Mocha;
        else
            this.coffee = Latte;

       return new this.coffee(options);           
    }
}

TESTING
---------
c = new CoffeeFactory();
c.getCoffee({type:"expresso"})
// returns: Expresso {shots: 3, sugar: 1, coffeeType: 1}
c.getCoffee({type:"latte",shots:4})
// returns: Latte {shots: 4, sugar: 4, coffeeType: 3}
```