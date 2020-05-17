## Contents

1. [Arrays](#arrays)

## **Arrays**

###### Some examples to work with arrays

```javascript
const animals = ['dog', 'cat', 'bird', 'tiger', 'elephant'];
const foods = [
    { name: 'apple', type: 'fruit', price: 0.50},
    { name: 'tuna', type: 'fish', price: 2.50},
    { name: 'banana', type: 'fruit', price: 1},
    { name: 'carrot', type: 'vegetables', price: 0.20},
    { name: 'onion', type: 'vegetables', price: 0.40},
    { name: 'cinnamon', type: 'spices', price: 1.50},
    { name: 'black beans', type: 'legumes', price: 1},
    { name: 'lentils', type: 'legumes', price: 0.80}
]
```

**Find**

1. ***Find a word in array***

```javascript
let findTiger = animals.find(item => {
    return (/tiger/g).test(item);
});  // return 'tiger' 

let findTigerShort = (arr, value) => arr.find(item => item === value)
findTigerShort(animals,'tiger'); // return 'tiger'

let findApple = foods.find(item => {
    return (/apple/g).test(item.name);
});  // return { name: 'apple', type: 'fruit', price: 0.5 }
```

**Map**
1. ***Convert first letter to uppercase***
```javascript
let toUpperFirstLetter = animals.map(item => {
    return item.charAt(0).toUpperCase() + item.slice(1);
}); // return [ 'Dog', 'Cat', 'Bird', 'Tiger', 'Elephant' ]

let toUpperFirstLetterShort = (arr) => arr.map(item => item.charAt(0).toUpperCase() + item.slice(1));
toUpperFirstLetterShort(animals); // return [ 'Dog', 'Cat', 'Bird', 'Tiger', 'Elephant' ]

```
2. ***Add VAT to the price***
```javascript
let priceAddIva = foods.map(item => {
    let new_precio = (item.price + item.price*0.21).toFixed(2);
    return {...item, precio: new_precio};
});  // return an array with a price updated
```

**Filter**
1. ***Filter by type***
```javascript
let filterFruits = foods.filter(item => {
    return item.type === 'fruit';
});

let filterFruitsShort = (arr, value) => arr.filter(item => item.type === value);
filterFruitsShort(foods,'fruit');

// return [ { name: 'apple', type: 'fruit', price: 0.5 }, { name: 'banana', type: 'fruit', price: 1 } ] 
```

**Every**
1. ***Check if all the words have a vowel***
```javascript
let checkLetter = animals.every(item => {
    return item.indexOf('i') !== -1;
}); // return false
```
2. ***Check if all foods are fruit***

```javascript
let checkFruits = foods.every(item => {
    return item.type === 'fruit';
}); // return false

let checkFruitsShort = (arr, value) => arr.every(item => item.type === value);
checkFruitsShort(foods,'fruit'); // return false
```

**Some**
1. ***Check if all the words have a vowel***
```javascript
let checkLetterSome = animals.some(item => {
    return item.indexOf('i') !== -1;
}); //return true

```
2. ***Check if all foods are fruit***
```javascript
let checkFruitsSome = foods.some(item => {
    return item.type === 'fruit';
}); //return true

let checkFruitsSomeShort = (arr, value) => arr.some(item => item.type === value);
checkFruitsSomeShort(foods,'fruit');  //return true
```

**Reduce**
1. ***Return a longest word***
```javascript
let longestWord = (longItem, currentWord) => currentWord.length > longItem.length ? currentWord : longItem;
animals.reduce(longestWord,''); // return elephant
```
2. ***Return the sum of prices***
```javascript
let precioTotal = foods.reduce((total, item) => {
    return total + item.price;
}, 0); // return price total: 7.9

let precioTotalShort = arr => arr.reduce((total,item) => total + item.price, 0);
precioTotalShort(foods); // return price total: 7.9
```





