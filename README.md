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
	nocturnal: false, 
	numLegs: 4,
	feedingRoutine: function(){
		console.log("20Lbs of beef, three times a day. Feed through fence.")
	}
}
```	


 