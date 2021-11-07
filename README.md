# The Dots

The Dots is a web application which helps you manage 2D points and calculate the squares they form.
It consists of a Backend REST server and Frontend Single-Page application.

The features include:
* Ability to add and delete individual points by coordinates, group them to lists 
* Finds all the possible squares by given points (including nested ones)
* Ability to bulk upload and download points
* All points are persisted on MongoDB Database

Architecture highlights:
* Backend module uses Spring Framework and core domain logic is decoupled to separate module making it delivery-agnostic
and easy to change to different kind of backend framework if needed 
* Uses Database adapter module to make core domain logic independent of Database technologies making it easy to change 
to different kind of Database server if needed
* Made according to SOLID practices

### Setup
In order to start up the stack you should have this software installed:

JDK 8+

Running MongoDB

Node.js and npm

Python2 (for npm sub-dependencies)

### Project setup

Clone all of these repositories to this project directory before starting:

1. https://github.com/andriusdgt/the-dots-backend
2. https://github.com/andriusdgt/the-dots-frontend
3. https://github.com/andriusdgt/the-dots-core
4. https://github.com/andriusdgt/the-dots-mongo-adapter

### Booting up
To start the Frontend you should execute these commands in Terminal from current directory:
```
    cd the-dots-frontend
    npm run start
```
To start the Backend you should execute these commands in another Terminal window from current directory:
```
    ./gradlew build :the-dots-backend:run
```
If you wish to start it using the *fat-jar* run:
```
    ./gradlew build
    cd the-dots-backend/build/libs
    java -jar the-dots-backend-1.0.0-all.jar
```

After both of the servers are booted up you can start using the web app from browser by 
inputting the address: ```http://localhost:8000```

For input, you can upload the dot files under this project `dataset` directory.
When creating points manually make sure to create a point list first.

### Credits

Square search algorithm was inspired from this scientific paper:

Kreveld, Marc J. van and Mark de Berg. “Finding Squares and Rectangles in Sets of Points.” WG (1989)
