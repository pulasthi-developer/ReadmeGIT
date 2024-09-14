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
The system follows the MVC (Model-View-Controller) architecture and is built using modern technologies:
* Backend: Node.js with Express.js framework for the REST API.
* Frontend: A single-page application built using Vue.js.
* Database: MongoDB for storing train locations, routes, schedules, and user data.

## Data Flow
1.	IoT devices transmit live location data every minute.
2.	Transmit location data via a mobile network to the REST API server.
3.	The REST API processes and stores the data in the MongoDB database.
4.	Client application retrieve data from REST API to display the live train locations on map.

## Data Modals

| **Entity**        | **Attributes**                                                   |
|-------------------|------------------------------------------------------------------|
| **Train**         | train_id, train_number, train_name, type                         |
| **Station**       | station_id, station_name, latitude, longitude                    |
| **Schedule**      | schedule_id, train_id, route_id, start_time, end_time            |
| **Train Route**   | route_id, route_name, start_station_id, end_station_id, distance |
| **Location**      | location_id, train_id, latitude, longitude, time_stamp           |
| **Real Location** | train_id, latitude, longitude, time_stamp                        |

