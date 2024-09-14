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
I used MVC architecture for this API-based Real-Time Train Tracking System project. MVC is short for Model, View, and Controller.

##### Models:
* Data Tables (Collections) handlings layer.

##### Controller:
* Interacts and handle requests related to Models and Routes.

##### Routes:
* Handle requests related to API.

##### View:
* User interface developed as separate app by using Vue.js. Get data from API and request data from API.

## Data Flow
1.	IoT devices transmit live location data every minute.
2.	Transmit location data via a mobile network to the REST API server.
3.	The REST API processes and stores the data in the MongoDB database.
4.	Client application retrieve data from REST API to display the live train locations on map.

## Data Modals

| **Entity**        | **Attributes**                                                   |
|-------------------|------------------------------------------------------------------|
| **Train**         | **'train_id'**, train_number, train_name, type                         |
| **Station**       | **'station_id'**, station_name, latitude, longitude                    |
| **Schedule**      | **'schedule_id'**, train_id, route_id, start_time, end_time            |
| **Train Route**   | **'route_id'**, route_name, start_station_id, end_station_id, distance |
| **Location**      | **'location_id'**, train_id, latitude, longitude, time_stamp           |
| **Real Location** | **'train_id'**, latitude, longitude, time_stamp                        |

## API Design

### RESTful API End Points

| **Model**     | **Route**                 | **Method** | **Description**                             |
|:-------------:|:-------------------------:|:----------:|:-------------------------------------------:|
| Train         | /trains                   | GET        | Get all Trains                              |
| Route         | /train-routes             | GET        | Get all Routes                              |
| Station       | /stations                 | GET        | Get all Stations                            |
| Schedule      | /schedules                | GET        | Get all Schedules                           |
| Real-Location | /real-location/{train_id} | GET        | Get Real Location data of specific Train    |
|               | /save-real-location       | POST       | Update Real Location data of specific Train |
| Location      | /locations                | GET        | Get all Location history                    |
|               | /save-location            | POST       | Save Location data to history               |


## Tech Stack

**1. Frontend Technologies**
- Vue.js - Front End JavaScript framework.
- HTML5 - Markup language used for structuring web page.
- CSS3 - Style sheet language used for styling of a HTML document.
- Bootstrap - CSS framework.
- JavaScript (ES6+) - Client side scripting language.
- Leaflet JavaScript Plugin - Use for Generate the Map.

**2. Backend Technologies (RESTful API Technologies)**
- Node.js - Uses JavaScript on the server.
- Express.js - Web application framework for developing RESTful APIs.
- Mongoose - JavaScript library that establishes a link between Node.js and MongoDB.

**3. Database Technologies**
- MongoDB -  Document-oriented database program (NoSQL).

## Deployment

- AWS EC2 (Amazon Elastic Compute Cloud) - Host backend on this server.

- AWS Amplify - Host frontend on this server.
