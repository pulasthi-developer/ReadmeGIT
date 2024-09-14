**NIBM Index: COBSCCOMPY4231P-002**

**Coventry Index: 14381838**

**Name: R. K. H. M. Ranawake**

# The Real-Time Train Tracking System - Sri Lanka

## Demo
**Goto [Web Site](https://www.livetrainlocation.xyz/)**

## Introduction
This project aims to track and display the real-time locations of trains across the country. The system's primary component is GPS-enabled IoT devices, which provide live location data. The project plans to install these IoT devices in each train engine to capture data at 1-minute intervals. The captured GPS data is transmitted to a central server for storage via a RESTful web API. The Client application (SPA) displays the real-time train location using that stored data.

## Key features
* IoT devices fitted on train engines, capture and sends GPS data with one-minute intervals to server through a mobile network.
* RESTful API to serve location data to multiple clients.
* Data retention for up to 90 days to analyze train routes and schedules.
* Responsive Single page web application to visualize the live train locations.

## System Architecture
We used MVC architecture for this API-based Real-Time Train Tracking System project. MVC is short for Model, View, and Controller.

* **Model** - Represents the data. It directly manages the data in this application.

* **View** - The user interface, which provides the user with data from the Model and relays user inputs back to the Controller.

* **Controller** - Handles input from the View, processes it and interacting with the Model

##### Models:
* locationModel.js - Location history data collection(table) model handlings JS file
* realLocationModel.js - Real-time Location data collection(table) model handlings JS file
* scheduleModel.js - Train schedule data collection(table) model handlings JS file
* stationModel.js - Station data collection(table) model handlings JS file
* trainModel.js - Train data collection(table) model handlings JS file
* trainRouteModel.js - Train route data collection(table) model handlings JS file
