# Constructors and Prototypal Inheritance
## Objective: 
> To understand Javascript Contsructors and Prototypal Inheritance
	
#### Constructor:
> Allows us to QUICKLY create javascript Objects

#### Prototypal Inheritance:
> Allows us share share and reuse code between Objects


<br><br>
______________________________________________________________________________
##	 What are we building:

#### We have a client with an [Animal Santuary](http://blackjaguarwhitetiger.org/visit-us/). 
* They want us to build software to keep track of the animals.  

* They recieve A LOT of animals. We need a way to quickly add more when they arrive.

* First [lets check out a few of their awesome animals](https://www.youtube.com/tv#/watch?v=vfCmzyLp26s&feature=youtu.be&t=439), so we know what are are in for. 
![](http://i.imgur.com/4wlZKb3.jpg)

* PS, I'm pretty sure this guy is gonna die soon. 

<br><br>
______________________________________________________________________________
## What we need to model:
* 12 Lions
* 15 Tigers
* 2 House Cats
* 2 Owls

#### One Way
We could use objects like we've seen before:
```javascript
var Simba = {
	name: "Simba",
	species: "Lion", 
	dangerLevel: 9,	
	nocturnal: false, 
	numberOfLegs: 4,
	feedingRoutine: function(){
		console.log("20Lbs of beef, three times a day. Feed through fence.")
	}
}
```	

* But...... thats gonna get really crazy when we have dozens or hundreds of animals to create and maintain. 

<br><br>
______________________________________________________________________________
## Another Way: Constructors.
Constructors let us create  blueprint for a type of object (here an animal). We can then use the blue print over and over again. 

A Constructor for a Lion looks like this:

```javascript
function Lion(name){
	this.name = name;	
	this.species = "Lion";
	this.dangerLevel = 9;
	this.nocturnal = false;
	this.numberOfLegs = 4;
	this.feedingRoutine = function(){
		console.log("20Lbs of beef, three times a day. Feed through fence.");
	}
}
```	

Then if we want to create a few Lions quickly we can do it in one line:
```javascript
var simba = new Lion("Simba");
var leo = new Lion("Leo");
```
Now we can use these objects (Lions)
```javascript
console.log( simba.name ) //Output -> "Simba"
console.log( leo.dangerLevel ) //Output -> 9
```
<br><br>
### [So lets see a live demo](https://repl.it/C16y/1)
[![](http://cdn.churchm.ag/wp-content/uploads/2011/10/replit-edit-620x431.png)](https://repl.it/C16y/1)

<br><br>

### [Your Turn](https://repl.it/C1xn/5)


Follow the link and create a Constructor for a Tiger and Owl.

<br><br>
______________________________________________________________________________
## DRY it up with Inheritance:

* So now we can easily create a bunch of new animals in a single line. 
* But looking at the Lion and Tiger constructor we see a lot of shared code. 

Lion:
```javascript
function Lion(name, enclosure){
	this.name = name;
	this.enclosure = enclosure;
	this.species = "Lion";
	this.dangerLevel = 9;
	this.nocturnal = false;
	this.numberOfLegs = 4;
	this.feedingRoutine = function(){
		console.log("20Lbs of beef, three times a day. Feed through fence.");
	}
}
```

Tiger:
```javascript
function Tiger(name, enclosure){
	this.name = name;	
	this.enclosure = enclosure;	
	this.species = "Tiger";
	this.dangerLevel = 8;
	this.nocturnal = false;
	this.numberOfLegs = 4;
	this.feedingRoutine = function(){
		console.log("10Lbs of beef, twice times a day.");
	}
}
```

### A Tiger and Lion can inhert properties of an Animal.  

Animal:
```javascript
function Animal(name, enclosure){
	this.name = name;	
	this.enclosure = enclosure;
	this.nocturnal = false;
	this.numberOfLegs = 4;
}
```
Lion:
```javascript
function Lion(name){
	this.name = name;	
	this.species = "Lion";
	this.dangerLevel = 9;
	this.feedingRoutine = function(){
		console.log("20Lbs of beef, three times a day. Feed through fence.");
	}
}
```

But we need to setup the inheritance:
```javascript 
Lion.prototype = new Animal():
```

Now all the properties on **Animal** are also on **Lion**

<br><br>
### [Cool, but lets see it for reals](https://repl.it/C2A9/2)
On in a live session



