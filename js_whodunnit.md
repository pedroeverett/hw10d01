# JS Day 1 Homework

Go through each sample code and work out what the output will be and explain what happened.

### Episode 1
```js
var name = 'Keith';

var printName = function() {
  console.log('My name is ' + name );
};

printName();

```
The output will be "My name is Keith". The function inside printName, when called, will use the value of var name.

### Episode 2
```js
score = 5;

var result = function() {
  var score = 3;
  return score;
};

console.log(result());

```
The output will be "3". The function inside result, when called, will use the value of the local var score.


### Episode 3
```js
var myAnimals = ['Chickens', 'Cats', 'Rabbits'];

var listAnimals = function() {
  myAnimals = ['Ducks', 'Dogs', 'Lions'];
  for(var i=0;i<myAnimals.length; i++){
    console.log(i + ": " + myAnimals[i]);
  }
}

listAnimals();

```
The output will be:
0: Ducks
1: Dogs
2: Lions
The function inside listAnimals, when called, local myAnimals will change the values of the global var myAnimals.


### Episode 4

```js
var suspectOne = 'Jay';
var suspectTwo = 'Val';
var suspectThree = 'Keith';
var suspectFour = 'Rick';

var allSuspects = function() {
  var suspectThree = 'Harvey'
  console.log('Suspects include: ' + suspectOne + ', ' + suspectTwo + ', ' + suspectThree + ', ' + suspectFour)
};

allSuspects();
console.log( 'Suspect three is:' + suspectThree );
```
The output will be:
Suspects include: Jay, Val, Harvey, Rick
Suspect three is:Keith
The function inside allSuspects, when called, will use local var suspectThree instead of the values of the global var suspectThree. On the last console.log the suspectThree that is called is the global var suspectThree

### Episode 5

```js
var detective = {
  name : 'Ace Ventura',
  pet : 'monkey'
};

var printName = function(detective) {
  return detective.name
};

var detectiveInfo = function() {
  detective['name'] = 'Poirot'
  return printName(detective);
};

console.log(detectiveInfo());
```
The output will be: "Poirot", on var detectiveInfo function we are using the "detective['name'] = 'Poirot'" to change the value of the name defined in the var detective.

### Episode 6
```js
var murderer = 'rick';

var outerFunction = function() {
  var murderer = 'marc';

  var innerFunction = function() {
    murderer = 'valerie';
  }

  innerFunction();
}

outerFunction();
console.log('the murderer is ', murderer);
```
The output will be: "the murderer is  rick". When we call outerFunction nothing changes, so when we call console.log on the murderer, it call the global var murderer.


### Episode 7 - Make up your own episode/s!

Make up your own episode which can be whatever you wish and the rest of the class will work out together what happened and what the output will be.
```js
var carList = ["Mercedes", "Bmw", "Audi"];
function printCars(array) {
  carList = ["car is,"];
  for (var i = 0; i < array.length; i++) {
    console.log("Car brand number " + i + " is " + array[i]);
    console.log("Next " + carList);
  }
}
printCars(carList);
```