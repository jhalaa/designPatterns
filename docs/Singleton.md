---
id: Singleton
title: Singleton Design Pattern
sidebar_label: Singleton Design Pattern
---

## About

Singleton design pattern is a design pattern which restricts the instantiation of a class to one object. This is useful when we need just one object to coordinate across the system. Repeated calls to the constructor of this object return the same object, once it has been created.
Let us take the real world example of a coffee maker. we just want one coffee maker to be instantiated in our system.
This coffee maker then proceeds to create many different types of coffee.(We are a small coffee shop and we just have one coffee maker).

## Code
```js

class MySingletonCoffeeMaker {
   
    constructor(){
        if(!MySingletonCoffeeMaker.instance){
            MySingletonCoffeeMaker.instance=this;
        }
        return MySingletonCoffeeMaker.instance;
    }

    makeCoffee() {
    	console.log("Making coffee !!!")
    }

    getSingletonData() {
        return MySingletonCoffeeMaker.instance;
    }
}


TESTING
--------
var one = new MySingletonCoffeeMaker();
var two = new MySingletonCoffeeMaker();
one==two
// prints true
```