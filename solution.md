#### Step 0

```
var launchpad;

launchpad = function() {
  console.log("Initiating Preflight Checks!");
}

launchpad();
```

#### Step 1

```
var launchpad;

function Ship(name) {
  this.name = name;
}

ourShip = new Ship("Serenity");

launchpad = function(spaceship) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
}

launchpad(ourShip);

```

#### Step 2
```
var launchpad;
var crewNames;
var trainCrew;

crewNames = ["Juice", "JRod", "Jelsea", "Jesse", "Jarvis"]

function CrewMember(name) {
  this.name = name;
  this.trained = false;
}

function Ship(name) {
  this.name = name;
}

ourShip = new Ship("Serenity");

launchpad = function(spaceship) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
}

launchpad(ourShip);
```

#### Step 3
```
var launchpad;
var crewNames;
var trainCrew;
var crewMembers;

crewNames = ["Juice", "JRod", "Jelsea", "Jesse", "Jarvis"]

function CrewMember(name) {
  this.name = name;
  this.trained = false;
}

trainCrew = function(untrainedCrewNamesArray) {
  crew = [];
  for(var i = 0; i < untrainedCrewNamesArray.length; i++) {
    newTrainee = new CrewMember(untrainedCrewNamesArray[i]);
    newTrainee.trained = true;
    crew.push(newTrainee);
  }
  return crew;
}

function Ship(name) {
  this.name = name;
}

ourShip = new Ship("Serenity");

launchpad = function(spaceship) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
}

launchpad(ourShip);
crewMembers = trainCrew(crewNames);
```

#### Step 4

```
var launchpad;
var crewNames;
var trainCrew;
var crewMembers;

crewNames = ["Juice", "JRod", "Jelsea", "Jesse", "Jarvis"]

function CrewMember(name) {
  this.name = name;
  this.trained = false;
}

trainCrew = function(untrainedCrewNamesArray) {
  crew = [];
  for(var i = 0; i < untrainedCrewNamesArray.length; i++) {
    newTrainee = new CrewMember(untrainedCrewNamesArray[i]);
    newTrainee.trained = true;
    crew.push(newTrainee);
  }
  return crew;
}

function Ship(name) {
  this.name = name;
  this.crew = [];
}

Ship.prototype.loadCrew = function(trainedCrew) {
  for(var i = 0; i < trainedCrew.length; i++) {
    this.crew.push(trainedCrew[i]);
    console.log("Welcome aboard, " + trainedCrew[i].name);
  }
}

crewMembers = trainCrew(crewNames);
ourShip = new Ship("Serenity");

launchpad = function(spaceship, unboardedCrew) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
  spaceship.loadCrew(unboardedCrew);
}

launchpad(ourShip, crewMembers);
```

#### Step 5
```
var launchpad;
var crewNames;
var trainCrew;
var crewMembers;

crewNames = ["Juice", "JRod", "Jelsea", "Jesse", "Jarvis"]

function CrewMember(name) {
  this.name = name;
  this.trained = false;
}

trainCrew = function(untrainedCrewNamesArray) {
  crew = [];
  for(var i = 0; i < untrainedCrewNamesArray.length; i++) {
    newTrainee = new CrewMember(untrainedCrewNamesArray[i]);
    newTrainee.trained = true;
    crew.push(newTrainee);
  }
  return crew;
}

function Ship(name) {
  this.name = name;
  this.crew = [];
}

Ship.prototype.loadCrew = function(trainedCrew) {
  for(var i = 0; i < trainedCrew.length; i++) {
    this.crew.push(trainedCrew[i]);
    console.log("Welcome aboard, " + trainedCrew[i].name);
  }
};

Ship.prototype.captain = function() {
  var crewCount = this.crew.length;
  return this.crew[Math.floor(Math.random() * crewCount)]
}

crewMembers = trainCrew(crewNames);
ourShip = new Ship("Serenity");

launchpad = function(spaceship, unboardedCrew) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
  spaceship.loadCrew(unboardedCrew);
}

launchpad(ourShip, crewMembers);
```

#### Step 6

```
var launchpad;
var crewNames;
var trainCrew;
var crewMembers;

crewNames = ["Juice", "JRod", "Jelsea", "Jesse", "Jarvis"]

function CrewMember(name) {
  this.name = name;
  this.trained = false;
}

trainCrew = function(untrainedCrewNamesArray) {
  crew = [];
  for(var i = 0; i < untrainedCrewNamesArray.length; i++) {
    newTrainee = new CrewMember(untrainedCrewNamesArray[i]);
    newTrainee.trained = true;
    crew.push(newTrainee);
  }
  return crew;
}

function Ship(name) {
  this.name = name;
  this.crew = [];
}

Ship.prototype.loadCrew = function(trainedCrew) {
  for(var i = 0; i < trainedCrew.length; i++) {
    this.crew.push(trainedCrew[i]);
    console.log("Welcome aboard, " + trainedCrew[i].name);
  }
};

Ship.prototype.captain = function() {
  var crewCount = this.crew.length;
  return this.crew[Math.floor(Math.random() * crewCount)]
}

crewMembers = trainCrew(crewNames);
ourShip = new Ship("Serenity");

launchpad = function(spaceship, unboardedCrew) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
  spaceship.loadCrew(unboardedCrew);
  var captain = spaceship.captain();
  console.log("High-five to the captain of this vessel, " + captain.name);
}

launchpad(ourShip, crewMembers);

```

#### Step 7
```
var launchpad;
var crewNames;
var trainCrew;
var crewMembers;
var rocket;

rocket = {
  fuel: 0,
  addFuel: function(fuelAmount) {
    this.fuel += fuelAmount;
    console.log("Rocket now has " + this.fuel + " liters of fuel");
  }
}

crewNames = ["Juice", "JRod", "Jelsea", "Jesse", "Jarvis"]

function CrewMember(name) {
  this.name = name;
  this.trained = false;
}

trainCrew = function(untrainedCrewNamesArray) {
  crew = [];
  for(var i = 0; i < untrainedCrewNamesArray.length; i++) {
    newTrainee = new CrewMember(untrainedCrewNamesArray[i]);
    newTrainee.trained = true;
    crew.push(newTrainee);
  }
  return crew;
}

function Ship(name) {
  this.name = name;
  this.crew = [];
  this.propulsion = null;
}

Ship.prototype.loadCrew = function(trainedCrew) {
  for(var i = 0; i < trainedCrew.length; i++) {
    this.crew.push(trainedCrew[i]);
    console.log("Welcome aboard, " + trainedCrew[i].name);
  }
}

Ship.prototype.captain = function() {
  var crewCount = this.crew.length;
  return this.crew[Math.floor(Math.random() * crewCount)]
}

crewMembers = trainCrew(crewNames);
ourShip = new Ship("Serenity");

launchpad = function(spaceship, unboardedCrew, propulsion) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
  spaceship.loadCrew(unboardedCrew);
  var captain = spaceship.captain();
  console.log("High-five to the captain of this vessel, " + captain.name);
}

launchpad(ourShip, crewMembers);
```

#### Step 8
```
var launchpad;
var crewNames;
var trainCrew;
var crewMembers;
var rocket;

rocket = {
  fuel: 0,
  addFuel: function(fuelAmount) {
    this.fuel += fuelAmount;
    console.log("Rocket now has " + this.fuel + " liters of fuel");
  },
  fire: function() {
    if(this.fuel > 0) {
      this.fuel -= 1;
      console.log("The engines have been fired!");
      console.log("Current fuel level is " + this.fuel);
      return true;
    } else {
      console.log("Engines failed to fire!  Please refuel");
      return false;
    }
  }
}

crewNames = ["Juice", "JRod", "Jelsea", "Jesse", "Jarvis"]

function CrewMember(name) {
  this.name = name;
  this.trained = false;
}

trainCrew = function(untrainedCrewNamesArray) {
  crew = [];
  for(var i = 0; i < untrainedCrewNamesArray.length; i++) {
    newTrainee = new CrewMember(untrainedCrewNamesArray[i]);
    newTrainee.trained = true;
    crew.push(newTrainee);
  }
  return crew;
}

function Ship(name) {
  this.name = name;
  this.crew = [];
  this.propulsion = null;
}

Ship.prototype.loadCrew = function(trainedCrew) {
  for(var i = 0; i < trainedCrew.length; i++) {
    this.crew.push(trainedCrew[i]);
    console.log("Welcome aboard, " + trainedCrew[i].name);
  }
}

Ship.prototype.captain = function() {
  var crewCount = this.crew.length;
  return this.crew[Math.floor(Math.random() * crewCount)]
}

crewMembers = trainCrew(crewNames);
ourShip = new Ship("Serenity");

launchpad = function(spaceship, unboardedCrew, propulsion) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
  spaceship.loadCrew(unboardedCrew);
  var captain = spaceship.captain();
  console.log("High-five to the captain of this vessel, " + captain.name);
}

launchpad(ourShip, crewMembers);

```

#### Step 9
```
var launchpad;
var crewNames;
var trainCrew;
var crewMembers;
var rocket;

rocket = {
  fuel: 0,
  addFuel: function(fuelAmount) {
    this.fuel += fuelAmount;
    console.log("Rocket now has " + this.fuel + " liters of fuel");
  },
  fire: function() {
    if(this.fuel > 0) {
      this.fuel -= 1;
      console.log("The engines have been fired!");
      console.log("Current fuel level is " + this.fuel);
      return true;
    } else {
      console.log("Engines failed to fire!  Please refuel");
      return false;
    }
  }
}

crewNames = ["Juice", "JRod", "Jelsea", "Jesse", "Jarvis"]

function CrewMember(name) {
  this.name = name;
  this.trained = false;
}

trainCrew = function(untrainedCrewNamesArray) {
  crew = [];
  for(var i = 0; i < untrainedCrewNamesArray.length; i++) {
    newTrainee = new CrewMember(untrainedCrewNamesArray[i]);
    newTrainee.trained = true;
    crew.push(newTrainee);
  }
  return crew;
}

function Ship(name) {
  this.name = name;
  this.crew = [];
  this.propulsion = null;
}

Ship.prototype.loadCrew = function(trainedCrew) {
  for(var i = 0; i < trainedCrew.length; i++) {
    this.crew.push(trainedCrew[i]);
    console.log("Welcome aboard, " + trainedCrew[i].name);
  }
}

Ship.prototype.captain = function() {
  var crewCount = this.crew.length;
  return this.crew[Math.floor(Math.random() * crewCount)]
}

Ship.prototype.mountPropulsion = function(unmountedPropulsion) {
  this.propulsion = unmountedPropulsion;
  console.log("Propulsion mounted!");
}

crewMembers = trainCrew(crewNames);
ourShip = new Ship("Serenity");

launchpad = function(spaceship, unboardedCrew, propulsion) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
  spaceship.loadCrew(unboardedCrew);
  var captain = spaceship.captain();
  console.log("High-five to the captain of this vessel, " + captain.name);
  spaceship.mountPropulsion(propulsion);
}

launchpad(ourShip, crewMembers, rocket);
```


## Step 10

```
var launchpad;
var crewNames;
var trainCrew;
var crewMembers;
var rocket;

rocket = {
  fuel: 0,
  addFuel: function(fuelAmount) {
    this.fuel += fuelAmount;
    console.log("Rocket now has " + this.fuel + " liters of fuel");
  },
  fire: function() {
    if(this.fuel > 0) {
      this.fuel -= 1;
      console.log("The engines have been fired!");
      console.log("Current fuel level is " + this.fuel);
      return true;
    } else {
      console.log("Engines failed to fire!  Please refuel");
      return false;
    }
  }
}

crewNames = ["Juice", "JRod", "Jelsea", "Jesse", "Jarvis"]

function CrewMember(name) {
  this.name = name;
  this.trained = false;
}

trainCrew = function(untrainedCrewNamesArray) {
  crew = [];
  for(var i = 0; i < untrainedCrewNamesArray.length; i++) {
    newTrainee = new CrewMember(untrainedCrewNamesArray[i]);
    newTrainee.trained = true;
    crew.push(newTrainee);
  }
  return crew;
}

function Ship(name) {
  this.name = name;
  this.crew = [];
  this.propulsion = null;
}

Ship.prototype.loadCrew = function(trainedCrew) {
  for(var i = 0; i < trainedCrew.length; i++) {
    this.crew.push(trainedCrew[i]);
    console.log("Welcome aboard, " + trainedCrew[i].name);
  }
}

Ship.prototype.captain = function() {
  var crewCount = this.crew.length;
  return this.crew[Math.floor(Math.random() * crewCount)]
}

Ship.prototype.mountPropulsion = function(unmountedPropulsion) {
  this.propulsion = unmountedPropulsion;
  console.log("Propulsion mounted!");
}

Ship.prototype.takeoff = function() {
  if (this.propulsion.fire()) {
    console.log("To infinity, and BEYOND");
  } else {
    console.log("takeoff unsuccessful!");
  }
}

crewMembers = trainCrew(crewNames);
ourShip = new Ship("Serenity");

launchpad = function(spaceship, unboardedCrew, propulsion) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
  spaceship.loadCrew(unboardedCrew);
  var captain = spaceship.captain();
  console.log("High-five to the captain of this vessel, " + captain.name);
  spaceship.mountPropulsion(propulsion);
  rocket.addFuel(100);
  spaceship.takeoff();
}

launchpad(ourShip, crewMembers, rocket);

```

## Step 11

```
var launchpad;
var crewNames;
var trainCrew;
var crewMembers;
var rocket;

rocket = {
  fuel: 0,
  addFuel: function(fuelAmount) {
    this.fuel += fuelAmount;
    console.log("Rocket now has " + this.fuel + " liters of fuel");
  },
  fire: function() {
    if(this.fuel > 0) {
      this.fuel -= 1;
      console.log("The engines have been fired!");
      console.log("Current fuel level is " + this.fuel);
      return true;
    } else {
      console.log("Engines failed to fire!  Please refuel");
      return false;
    }
  }
}

crewNames = ["Juice", "JRod", "Jelsea", "Jesse", "Jarvis"]

function CrewMember(name) {
  this.name = name;
  this.trained = false;
}

trainCrew = function(untrainedCrewNamesArray) {
  crew = [];
  for(var i = 0; i < untrainedCrewNamesArray.length; i++) {
    newTrainee = new CrewMember(untrainedCrewNamesArray[i]);
    newTrainee.trained = true;
    crew.push(newTrainee);
  }
  return crew;
}

function Ship(name) {
  this.name = name;
  this.crew = [];
  this.propulsion = null;
}

Ship.prototype.loadCrew = function(trainedCrew) {
  for(var i = 0; i < trainedCrew.length; i++) {
    this.crew.push(trainedCrew[i]);
    console.log("Welcome aboard, " + trainedCrew[i].name);
  }
}

Ship.prototype.captain = function() {
  var crewCount = this.crew.length;
  return this.crew[Math.floor(Math.random() * crewCount)]
}

Ship.prototype.mountPropulsion = function(unmountedPropulsion) {
  this.propulsion = unmountedPropulsion;
  console.log("Propulsion mounted!");
}

Ship.prototype.takeoff = function() {
  if (this.propulsion.fire()) {
    console.log("To infinity, and BEYOND");
  } else {
    console.log("takeoff unsuccessful!");
  }
}

crewMembers = trainCrew(crewNames);
ourShip = new Ship("Serenity");

launchpad = function(spaceship, unboardedCrew, propulsion) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
  spaceship.loadCrew(unboardedCrew);
  var captain = spaceship.captain();
  console.log("High-five to the captain of this vessel, " + captain.name);
  spaceship.mountPropulsion(propulsion);
  rocket.addFuel(100);
  spaceship.takeoff();
}

coolShipNames = ["Starship Enterprise", "Galaxy Quest", "Nerd Rage"]

fleet = {
  name: "Fleetwood Mac",
  ships: [],
  build: function(shipNames) {
    for(var i = 0; i < shipNames.length; i++) {
      var newShip = new Ship(shipNames[i]);
      this.ships.push(newShip);
      console.log("Welcome, " + newShip.name + ", to the best fleet ever: " + this.name);
    }
  }
}

launchpad(ourShip, crewMembers, rocket);

fleet.build(coolShipNames);

```

##Step 12

```
var launchpad;
var crewNames;
var trainCrew;
var crewMembers;
var rocket;

rocket = {
  fuel: 0,
  addFuel: function(fuelAmount) {
    this.fuel += fuelAmount;
    console.log("Rocket now has " + this.fuel + " liters of fuel");
  },
  fire: function() {
    if(this.fuel > 0) {
      this.fuel -= 1;
      console.log("The engines have been fired!");
      console.log("Current fuel level is " + this.fuel);
      return true;
    } else {
      console.log("Engines failed to fire!  Please refuel");
      return false;
    }
  }
}

crewNames = ["Juice", "JRod", "Jelsea", "Jesse", "Jarvis"]

function CrewMember(name) {
  this.name = name;
  this.trained = false;
}

trainCrew = function(untrainedCrewNamesArray) {
  crew = [];
  for(var i = 0; i < untrainedCrewNamesArray.length; i++) {
    newTrainee = new CrewMember(untrainedCrewNamesArray[i]);
    newTrainee.trained = true;
    crew.push(newTrainee);
  }
  return crew;
}

function Ship(name) {
  this.name = name;
  this.crew = [];
  this.propulsion = null;
}

Ship.prototype = {
  constructor: Ship,
  loadCrew: function(trainedCrew) {
    for(var i = 0; i < trainedCrew.length; i++) {
      this.crew.push(trainedCrew[i]);
      console.log("Welcome aboard, " + trainedCrew[i].name);
    }
  },
  captain: function() {
    var crewCount = this.crew.length;
    return this.crew[Math.floor(Math.random() * crewCount)]
  },
  mountPropulsion: function(unmountedPropulsion) {
    this.propulsion = unmountedPropulsion;
    console.log("Propulsion mounted!");
  },
  takeoff: function() {
    if (this.propulsion.fire()) {
      console.log("To infinity, and BEYOND");
    } else {
      console.log("takeoff unsuccessful!");
    }
  }
}

crewMembers = trainCrew(crewNames);
ourShip = new Ship("Serenity");

launchpad = function(spaceship, unboardedCrew, propulsion) {
  console.log("Initiating Preflight Checks!");
  console.log("The name of our ship is " + spaceship.name);
  spaceship.loadCrew(unboardedCrew);
  var captain = spaceship.captain();
  console.log("High-five to the captain of this vessel, " + captain.name);
  spaceship.mountPropulsion(propulsion);
  rocket.addFuel(100);
  spaceship.takeoff();
}

coolShipNames = ["Starship Enterprise", "Galaxy Quest", "Nerd Rage"]

fleet = {
  name: "Fleetwood Mac",
  ships: [],
  build: function(shipNames) {
    for(var i = 0; i < shipNames.length; i++) {
      var newShip = new Ship(shipNames[i]);
      this.ships.push(newShip);
      console.log("Welcome, " + newShip.name + ", to the best fleet ever: " + this.name);
    }
  }
}

launchpad(ourShip, crewMembers, rocket);

fleet.build(coolShipNames);

```
