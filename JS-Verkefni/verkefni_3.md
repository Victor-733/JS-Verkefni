## 1
#### Útskýrðu hvernig objectar tengjast í JavaScript.
Þegar þú býrð til object í JavaScript þá á sá object einhvern pabba sem hann tengist í eða prototype. Það þýðir að objectið sem er undir pabbanum á líka öll methods sem að pabbinn er með í sér. t.d.
```js
let animal = {
  eats: true
};
let rabbit = {
  jumps: true
};

rabbit.__proto__ = animal; // lína sem að tengir rabbit við animal sem er pabbinn

alert( rabbit.eats ); // skilar: true
```

## 2
#### Útskýrðu kóðann línu fyrir línu. 
```js
function Book(isbn) {
    this.isbn = isbn;
}
Book.prototype.getIsbn = function () {
    return "Isbn is " + this.isbn;
};

let bookObject = new Book(12345);
```
Í fyrstu tveim línunum er hann að búa til function sem heitir Book sem tekur inn gildið "isbn". (this.isbn = isbn) þýðir að this mun bara reference-a objectið sem kallar á það. 
    Svo bý ég til annað function sem er með prototype á
Book functionið og það skilar streng sem að segir: ("Isbn is " + this.isbn) Þannig að þegar ég bý til bookObject niðri sem tekur í sig nýtt Book function þá get ég líka notað getIsbn function-ið sem ég tengdi við Book áðan.

## 3
#### Prototypal pattern

1. 
```js
function Spaceship(name){
    this.name = name;
    this.speed = 10;
    this.life = 10;
}

let f1 = new Spaceship("Celina");
let f2 = new Spaceship("BC Collossus");
let f3 = new Spaceship("Independance");
```
2. 
```js
f3.speed = 6;
f2.speed = 15;
f1.speed = 11;
```
3. 
```js
Spaceship.prototype.fly = function(){
        ++this.speed;
}
```
4. 
```js
f1.setLife = function(){
    ++this.life;
}
```

## 4
#### Gerðu það sama (sambærilegt) og síðasta lið en með notkun class. Notaðu eftir þörfum; constructor, get, set, static, extends, super, mix-ins.
```js
class Spaceship {
    constructor(name) {
        this.name = name;
        this.speed = 10;
        this.life = 10;
    }

    fly() {
        ++this.speed;
    }
}

let f1 = new Spaceship("Celina");
let f2 = new Spaceship("BC Collossus");
let f3 = new Spaceship("Independance");

f1.setLife = function(){
    ++this.life;
}
```

## 5
#### Hver er munurinn á Class og Prototype?
Class er nýrri og hentugari leið til þess að gera það sem var gert í dæmi 3. Mörgum finns kannski þægilegara að nota class í staðin vegna þess að það er líka notað í vinælum tungumálum eins og python. 