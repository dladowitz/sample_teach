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
	numLegs: 4,
	feedingRoutine: function(){
		console.log("20Lbs of beef, three times a day. Feed through fence.")
	}
}
```	

* But...... thats gonna get really crazy when we have dozens or hundreds of animals to create and maintain. 

#### Another Way: Constructors.
Constructors let us create  blueprint for a type of object(or animal). We can then use the blue print over and over again. 

A Constructor for a Lion looks like this:

```javascript
function Lion(name){
	this.name = name;	
	this.species = "Lion";
	this.dangerLevel = 9;
	this.nocturnal = false;
	this.numLegs = 4;
	this.feedingRoutine = function(){
		console.log("20Lbs of beef, three times a day. Feed through fence.");
	}
}
```	

Then if we want to create a few Lions quickly we do:
```javascript
var simba = new Lion("Simba");
var leo = new Lion("Leo");
```
Now we can use these objects (Lions)
```javascript
console.log simba.name //Output -> "Simba"
console.log leo.name //Output -> "Leo"
```

 