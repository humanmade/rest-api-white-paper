# CASE STUDY: NOMADBASE

[Nomadbase](http://nomadbase.io) is a service that facilitates remote working and the digital nomad way of life. Using public APIs, it aggregates data from social networking services to create a map of nomad locations across the world.
> Our development team has a lot of experience with WordPress, and recognises its ability to provide a solid foundation to build an application on. Leveraging its users system for signups, the REST API for all external communication, and extremely common server requirements, we were able to get the prototype up and running in a matter of days, rather than weeks or months. We used the REST API for not only the communication with the frontend application, but also inbound data coming from Facebook and Foursquare to collect user location data.

Joe Hoyle, Nomadbase## Why use WordPress and the REST API?

WordPress enabled the developers to get the first version of Nomadbase up and running quickly, providing both a stable central platform where data can be aggregated and an API for delivering the data to the frontend.

## The build

Nomadbase uses APIs to gather geodata from Facebook, Swarm, Twitter, Instagram, and TripIt. This data is stored in custom tables in the MySQL database. Data is then sent over the WordPress REST API to a React frontend and displayed in the browser. [Leaflet](http://leafletjs.com/) is used to create overlays on the map.

When a new user signs up for Nomadbase, data is requested from five different social networks. This leads to significant background processing. To speed this up, wp-cron is replaced by a system tool called [Cavalcade](https://github.com/humanmade/Cavalcade), developed by Human Made for large-scale WordPress installations

The next step for Nomadbase is a React Native iOS application that reuses code from the browser app. As all the data and user actions that exist for Nomadbase are processed by the REST API, no additional backend work needs to be done to build the new application.