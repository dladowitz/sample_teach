# Objective: 
> ## Understand Javascript Contsructors and Prototype Inheritance
	
#### Constructors:
> Allow us to QUICKLY create javascript Objects

#### Prototype Inheritance:
> Allow us share share and reuse code between Objects


<br><br>
______________________________________________________________________________
##	 What are we building:

#### We have a client with an [Animal Santuary](http://blackjaguarwhitetiger.org/visit-us/). 
* They want us to build software to keep track of the animals.  

* They recieve A LOT of animals. We need a way to quickly add more when they arrive.

* First <a target="_blank" href="https://www.youtube.com/tv#/watch?v=vfCmzyLp26s&feature=youtu.be&t=439">lets check out a few of their awesome animals</a>, so we know what are are in for. 
[![](http://i.imgur.com/4wlZKb3.jpg)](https://www.youtube.com/tv#/watch?v=vfCmzyLp26s&feature=youtu.be&t=439)


* PS, I'm pretty sure this guy is gonna die soon. 

<br><br>
______________________________________________________________________________
## What we need to model:
* 30 Lions
* 25 Tigers
* 28 Jaguars
* 20 Lepards
* 10 House Cats
* 20 Dogs
* 2 Owls

#### One Way
We could use objects like we've seen before:

```javascript
var simba = {
	name: "Simba",
	species: "Lion",
	family: "Felidae",
	dangerLevel: 9,	
	numberOfLegs: 4,
	carinvore: true,
	tail: true,
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
	this.family = "Felidae";
	this.dangerLevel = 9;	
	this.numberOfLegs = 4;
	this.carinvore = true;
	this.tail = true;
	this.feedingRoutine = function(){
		console.log("20Lbs of beef, three times a day. Feed through fence.")
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
### [So lets see a live demo](https://repl.it/C16y/9)
[![](http://cdn.churchm.ag/wp-content/uploads/2011/10/replit-edit-620x431.png)](https://repl.it/C16y/9)

<br><br>

### [Your Turn](https://repl.it/C1xn/10)


Follow the link and create a Constructor for a Tiger.

<br><br>
______________________________________________________________________________
## DRY it up with Inheritance:

* So now we can easily create a bunch of new animals in a single line. 
* But looking at the Lion and Tiger constructor we see a lot of shared code. 

### Lion:
<img src="http://kids.nationalgeographic.com/content/dam/kids/photos/animals/Mammals/H-P/lion-mom-cub.jpg" width="250">

```javascript
function Lion(name){
	this.name = name;	
	this.species = "Lion";
	this.family = "Felidae";
	this.dangerLevel = 9;	
	this.numberOfLegs = 4;
	this.carinvore = true;
	this.tail = true;
	this.feedingRoutine = function(){
		console.log("20Lbs of beef, three times a day. Feed through fence.")
	}
}
```
<br>
### Tiger:
<img src="http://kids.nationalgeographic.com/content/dam/kids/photos/animals/Mammals/Q-Z/tiger-mom-cub.jpg.adapt.945.1.jpg" width="250">

```javascript
function Tiger(name){
	this.name = name;	
	this.species = "Tiger";
	this.family = "Felidae";
	this.dangerLevel = 8;	
	this.numberOfLegs = 4;
	this.carinvore = true;
	this.tail = true;
	this.feedingRoutine = function(){
		console.log("10Lbs of beef, twice times a day.");
	}
}
```

### A Lion and Tiger can inhert properties of a Feline.  
<br>
### Feline:
<img src="http://2.bp.blogspot.com/-0VeZpoXrHuw/Tl2vI-ov1WI/AAAAAAAAADU/Iwci0QtQBFc/s1600/Greenlandic+felidae.jpg" width="350">

```javascript
function Feline(){
	this.family = "Felidae";
	this.numberOfLegs = 4;
	this.carinvore = true;
	this.tail = true;
}
```
### Lion:
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
Lion.prototype = new Feline():
```

Now all the properties on **Feline** are also on **Lion**

<br><br>
### [Cool, but lets see it for reals](https://repl.it/C2A9/7)
On in a live session



### [And your turn again](https://repl.it/C2BN/6)
Lets create an Animal and have Tigers and Owls inherit from them.


