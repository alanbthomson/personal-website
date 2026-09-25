---
date: 2026-04-22T21:28:29+09:00
title: Setawalk
summary: 'A Flutter navigation app using PostgreSQL/PostGIS and a custom algorithm to generate routes based on user preferences.'
description: 'A navigation app for explorers, built with PostGIS and Flutter.'
categories:
  - backend
  - web
tags:
  - postgresql
  - postgis
  - pl/pgsql
  - supabase
  - flutter
featured: true
cover:
  image: "images/setawalk/cover.webp"
  # can also paste direct link from external site
  # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
  alt: "Image of application showing a route generated for a user, along with visualizations of database data on a map."
  caption: "From left to right: Custom POI map, User interface showing a generated route, Raw OpenStreetMap data."
  relative: true # To use relative path for cover image, used in hugo Page-bundles
---

## Overview
This was the final graduation project for my Computer Science degree, developed as a team of four. I was primarily responsible for the backend database and routing algorithm, contributing approximately 80% of its development.

The goal of this project was to create a navigation application for people who want to explore their surroundings, rather than simply take the fastest route to their destination.

Setawalk allows users to choose a starting point and destination, adjust their preferences for different categories of points of interest, and generate a walking route that incorporates locations they may enjoy visiting along the way.

## Features

- Generate walking routes between two locations.
- Select relative preferences for shrines, shopping, cafes, and parks.
- Adjust the additional time they are willing to spend exploring.
- Save user preferences to their cloud account.
- View selected points of interest and the generated route on a map.
- Receive turn-by-turn walking instructions.

## Implementation
### Database

The backend uses PostgreSQL with PostGIS and pgRouting to store geographic data and calculate walking routes.

OpenStreetMap data was imported into a PostgreSQL database and processed into a pedestrian routing network. Points of interest were stored separately and given a record pointing to their nearest pedestrian routing node.

To connect these points of interest, a graph was generated using Delaunay triangulation. Each connection was then associated with a walking distance calculated through pgRouting using Dijkstra's algorithm. 

This allowed the application to treat points of interest as a network of possible stops, while still using the underlying pedestrian network to calculate the actual walking paths between them.

### Algorithm

The route generation algorithm combines typical shortest-path routing with preference-based point-of-interest selection.

Given a starting point and destination, the algorithm first generates an "as the crow flies" direct line between points A and B. It then casts the starting point to its nearest node on the navigation network, and generates Dijkstra paths to each potential POI connection in the direction of travel. 

The algorithm then selects POI stops based on factors including:

- The user's preferences for each category.
- Relative satiety of each category.
- The angle of the considered POI relative to the destination.
- The distance from the current point of interest.
- The distance remaining to the destination.


The algorithm gradually reduces the allowed deviation from the direct line as the route progresses. This encourages exploration near the beginning of the journey while ensuring that the route eventually returns toward the destination.

A satiety system also reduces the effective preference for categories that have already been visited, encouraging routes to include a variety of locations proportional to the users preferences.


### Frontend

The frontend was developed using Flutter and integrates with Google Maps for map visualization and location search.

Supabase is used to communicate with the backend, including requesting route generation and passing user preferences to the route generation system.

The application processes the returned route coordinates on the client side to calculate walking distance, estimated duration, and turn-by-turn instructions. Turns are detected by analysing changes in direction along the route.

## Challenges

- Learning how to obtain and process geographic data using PostGIS and pgRouting.
- Developing a route generation algorithm that balances user preferences with realistic walking directions.
- Generating a network of connections between points of interest using Delaunay triangulation.
- Learning PL/pgSQL to implement more complex database-side logic.
- Integrating a custom routing system with a mobile application and map visualization.

## Outcomes

This project gave me experience designing and implementing a GIS application across both the backend and frontend.

I gained a deeper understanding of spatial databases, PostgreSQL, graph-based pathfinding, and how geographic data can be processed to support applications beyond traditional navigation.

It also gave me experience developing a project where the database was responsible for a significant portion of the application's logic.

## Technologies Used
- Backend: PostgreSQL, PostGIS, pgRouting, PL/pgSQL, Supabase
- Frontend: Flutter, Dart
- APIs: Google Maps Platform
- Data: OpenStreetMap
