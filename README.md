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

##### Models:
* locationModel.js - Location history data collection(table) model handlings JS file
* realLocationModel.js - Real-time Location data collection(table) model handlings JS file
* scheduleModel.js - Train schedule data collection(table) model handlings JS file
* stationModel.js - Station data collection(table) model handlings JS file
* trainModel.js - Train data collection(table) model handlings JS file
* trainRouteModel.js - Train route data collection(table) model handlings JS file

##### Controller:
* locationController.js - Interacts with `locationModel.js` to handle requests related to location history and real-time location data.
* realLocationController.js - Interacts with `realLocationModel.js` to handle requests related real-time location data.
* scheduleController.js - Interacts with `scheduleModel.js` to handle requests related to train schedule data.
* stationController.js - Interacts with `stationModel.js` to handle requests related to train station data.
* trainController.js - Interacts with `trainModel.js` to handle requests related to train data.
* trainRouteController.js - Interacts with `trainRouteModel.js` to handle requests related to train route data.

##### Routes:
* `locationRouters.js,realLocationRouters.js,scheduleRoutes.js,stationRouters.js,trainRouteRouters.js` and `trainRouters.js` are handle requests related to API.

##### View:
* User interface developed as separate app by using Vue.js

## Data Flow
1.	IoT devices transmit live location data every minute.
2.	Data transmit through a mobile network to the REST API server.
3.	The REST API process and stores the data in the database.
4.	Client application access the data via REST API to display the live locations on map.

## Data Modals

| **Entity**        | **Attributes**                                                   | **Description**                   |
|-------------------|------------------------------------------------------------------|-----------------------------------|
| **Train**         | train_id, train_number, train_name, type                         | Store Train data                  |
| **Station**       | station_id, station_name, latitude, longitude                    | Store Station data                |
| **Schedule**      | schedule_id, train_id, route_id, start_time, end_time            | Store Schedule data               |
| **Train Route**   | route_id, route_name, start_station_id, end_station_id, distance | Store Train Route data            |
| **Location**      | location_id, train_id, latitude, longitude, time_stamp           | Store Train Location history data |
| **Real Location** | train_id, latitude, longitude, time_stamp                        | Store Train Real Location data    |

