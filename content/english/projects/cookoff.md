---
date: '2026-07-27T15:19:34+09:00'
title: 'Cookoff'
summary: 'Online game jam with the theme "little guys." An RTS cooking sim where the player commands units to prepare dishes.'
description: 'Online game jam with the theme "little guys." Player commands units to cook dishes in an RTS cooking sim.'
categories:
  - Game Dev
  - hackathon
tags:
  - godot
  - gdscript
featured: true
cover:
  image: "images/cookoff/cover.webp"
  alt: "Image showing the main menu of the Cookoff game, with title, start and exit buttons."
  caption: "Main menu of the game, featuring a little cook and a freeze frame of gameplay."
  relative: true # To use relative path for cover image, used in hugo Page-bundles
---

## Overview
This game was developed as part of the [Brainless Game Jam](https://itch.io/jam/brainless-game-jam) in a team of two.

The theme was announced as "little guys" and after some brainstorming, we came up with the idea of a cooking Real Time Strategy (RTS) game. Players control groups of little cooks who work together to complete stir-fry orders for customers.

## Features
- Unit control, including selection and groups of units
- Ingredient management and cooking simulation
- Order ticket generation and dish grading system
- Communication between UI elements and game logic
- Game state management and high score tracking

## Challenges
The main challenges were the limited timeframe combined with helping my teammate learn a new toolset (Godot). This was a great learning opportunity for both of us, where we worked to balance development progress with building up each other's understanding of the toolset and game logic.

One particularly interesting part of the project for me, was implementing a generic object pooler. This system was used to efficiently manage cooking ingredient resource instances.


## Tech Stack
- Godot
- GDScript

## Play the Game
The game is currently available on [itch.io](https://notkomiyaki.itch.io/cookoff).

<!--{{< itch
    game="18352517"
    width="1150"
    height="450"
>}}-->
