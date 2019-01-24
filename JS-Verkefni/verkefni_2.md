# 1
#### Búðu til object með upplýsingar um þig; nafn, kennitala, heimilsfang, heimasími og gsm.

```js
let me = {
    name: "Victor",
    age: 17,
    ssn: "161101-2220",
    address: "Kleppsvegur 38, 105 Rvk",
    phone: "+354 5811652",
    mobilePhone: "+354 6507715"
}
```

# 2
#### Notaðu for…in lykkjuna til að birta öll eigindin (e. property) ásamt gildum í objectinu í lið 1.

```js
for (let x in me){
    console.log(x + ": " + me[x]);
}
```

# 3
#### . Bættu við aðferð í objectið sem þú gerðir í lið 1. Aðferðin á að skila streng sem inniheldur nafn og aldur.
```js
function infoMe() {
    return("Ég heiti "+ me.name + " og ég er " + me.age + " ára gamall.")
}
```
# 4
#### Prentaðu út með console.log() Nonni. 
```js
let family = {
    "parents":{
        "fathers": [{"name":"Jakob"},{"name":"Nonni"}],
        "mothers":[{"name":"Rakel"},{"name":"Sara"}]
    }
 };
```
console.log() sem kallar á Nonna

```js
console.log(family.parents.fathers[1].name);
```

# 5
#### Leystu lið 8 í lesson 7 - Objects á Udacity
```js
let breakfast = {
    name: "The Lumberjack",
    price: "$9.95",
    ingredients: ["eggs", "sausage", "toast", "hashbrowns", "pancakes"]
};
```

# 6
#### Leystu lið 9 í lesson 7 - Objects á Udacity
```js
var savingsAccount = {
    balance: 1000,
    interestRatePercent: 1,
    deposit: function addMoney(amount) {
        if (amount > 0) {
            savingsAccount.balance += amount;
        }
    },
    withdraw: function removeMoney(amount) {
        var verifyBalance = savingsAccount.balance - amount;
        if (amount > 0 && verifyBalance >= 0) {
            savingsAccount.balance -= amount;
        }
    },
    // your code goes here
};

console.log(savingsAccount.printAccountSummary());
```

# 7
#### Leystu lið 12 í lesson 7 - Objects á Udacity
```js
var donuts = [
    { type: "Jelly", cost: 1.22 },
    { type: "Chocolate", cost: 2.45 },
    { type: "Cider", cost: 1.59 },
    { type: "Boston Cream", cost: 5.99 }
];

// your code goes here
donuts.forEach(function(a){
   console.log(a.type + " donuts cost $" + a.cost + " each") 
});
```

# 8
#### Eru öll eigindi (e. properties) í sömu röð og þeim var bætt í object, rökstuddu? 

Javascript raðar hlutum í objectum í sérstakri röð, númer eru röðuð eftir stærð og allt hitt er raðað eftir því hvernig þú settir það upp í kóðanum. Til dæmis ef þú ert að búa til object sem geymir númer fyrir öll símanúmer landanna.
```js
let codes = {
  "49": "Germany",
  "41": "Switzerland",
  "44": "Great Britain",
  "1": "USA"
};
// prentar...
> 1, 41, 44, 49
```
En ef þú myndir bæta einhverjum staf sem er ekki númer fyrir framan öll númerin...
```js
let codes = {
  "+49": "Germany",
  "+41": "Switzerland",
  "+44": "Great Britain",
  "+1": "USA"
};
// prentar...
> 49, 41, 44, 1
```

# 9
#### Útskýrðu hvað eftirfarandi kóði gerir.
```js
// býr til object sem heitir user og gefur honum nafn
let user = { name: "John" };
/* býr til breytu sem heitir admin sem bendir á upplýsingarnar
í user (ekki copy af user)*/
let admin = user;
```

# 10
#### Afhverju virkar eftirfarandi?
```js
const user = {
 name: "John"
};
user.age = 25;
alert(user.age); // 25
```
Það er ekkert að þessum kóða því að í línu 4 er hann ekki að breyta value-inu á *user* heldur er hann að setja inn í *user*. *user* er að vísa í sama object-ið allan tímann.

Ef við myndum reyna að breyta *user* í eitthvað annað þá kæmi villa
```js
const user = {
  name: "John"
};

// Error (can't reassign user)
user = {
  name: "Pete"
};
```