## 1. 
#### null
*null*
null er eitthvað sem er hægt að setja inn í breytu ef þú
vilt ekki setja eitthvað í hana ennþá svo þú setur eitthvað sem er ekkert í breytuna. null er ekki það sama og 0 það þíðir bara "ekkert".
```javascript
let x = null;
console.log(x);

> null
```
#### undefined
*undefined*
undefined þýðir að það er ekki enn
búið að setja neitt í
breytuna, það er ekki eitthvað sem táknar ekkert, það er að segja þér að það er ekkert í breytuni.
```javascript
let x;
console.log(x);

> undefined
```

## 2.
#### use strict
*use strict* er notað ef þú láta þýðandann vita að kóðinn á 
að vera strangari, til dæmis ef þú notar strict mode þá getur þú ekki búið til breytu án þess að tilgreina hvernig breyta hún er fyrst.
```javascript
"use strict";
x = "hallo";

> error
```

## 3.
#### var
 var breytur eru breytur sem að gleymast aldrei, ef þú býrð t.d. til var breytu inni í loop þá getur þú notað hana eftir að loop-ið er búið.
```javascript
{ 
  var x = 2; 
}
console.log(x);

> 2
```
#### let
let breytur eru öðruvísi á þann hátt að þegar þú býrt til let breytu inni í block þá getur þú ekki lengur notað hana fyrir utan blockina, hún eyðist eftir að þýðandinn fer yfir blockina.
```javascript
{ 
  let x = 2; 
}
console.log(x);

> error
```

#### const
const breytur virka alveg eins og let breytur nema það að það er ekki hægt að breyta gildinu á þeim.
```javascript
const PI = 3.141592653589793;
PI = 3.14; //get ekki breytt

> error
```

## 4.
#### án for lykkju
```javascript
let x = 9;
while (x >= 1) {
    console.log("hello " + x);
    x = x - 1;
}
```
#### með for lykkju
```javascript
for (x = 9; x >= 1; --x) {
    console.log("hello " + x);
}
```

## 5.
#### 1. Function Declaration
```js
function add(a, b) {
    return a + b;
}
```
#### 2. Function Expressions
```js
var add = function(a, b) {
  return a + b;
};
```
#### 3. Arrow Functions
```js
var add = (a, b) => a + b;
```

## 6.
```js
(function() { alert('Hello World'); })(); 

> Hello World
```
Það sem þetta fall gerir er að prenta út orðin "Hello World" í vafrann. Fyrstu tveir svigarnir eru fyrir functionið, svigarnir utan um fallið eru til þess að þýðandinn haldi ekki að það sé bara verið að skilgreina venjulegt fall. Svo eru þessir tveir svigar á endanum sem keyra fallið án þess að þurfa að kalla í það eftir að hafa tilgreint það.


## 7.
```js
"use strict";
let a = 1;
function b() {
 a = 10;
 return;
 function a() {}
}
b();
console.log(a);
```

```js
"use strict";
let a;
function b() {
    function a() {}
    a = 10;
    return;
}
a = 1;
b();
console.log(a);
```
Ástæðan afhverju það prentast 1 en ekki 10 er af því að JavaScript þýðandinn færir allar breytur og öll föll efst í línurnar og eins og sést í kóðanum eftir að ég endurraðaði honum þá er ég bara að breyta gildinu á fallinu a þegar ég segji a = 10 en ekki breytuni a sem að er global breyta.

## 8.
```js
var test = [12, 929, 11, 3, 199, 1000, 7, 1, 24, 37, 4,
    19, 300, 3775, 299, 36, 209, 148, 169, 299,
    6, 109, 20, 58, 139, 59, 3, 1, 139
];

// Write your code here
test.forEach(function(num, i) {
  if (num % 3 === 0){
      test[i] += 100;
  }
});
```

## 9.
```js
var bills = [50.23, 19.12, 34.01,
    100.11, 12.15, 9.90, 29.11, 12.99,
    10.00, 99.22, 102.20, 100.10, 6.77, 2.22
];

var totals = bills.map(function(price) {
  price *= 1.15;
  return Number(price.toFixed(2));
});
console.log(totals);
```

## 10.
#### stack overflow
```js
function a(){
    b();
}
function b() {
    a();
}
```