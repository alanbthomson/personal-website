---
date: "2025-03-29T18:34:42+09:00"
title: 'TUJ Hackathon'
summary: '8 hour low-level gamejam with the theme "The Game is a Lie"'
description: '8 hour low-level gamejam with the theme "The Game is a Lie"'
categories:
  - gamedev
  - hackathon
tags:
  - python
  - pygame
featured: true
cover:
  image: "images/keepaway/cover.webp"
  alt: "Image showing the game over state of the game, where the player was caught by the enemy."
  caption: "The player being caught by the enemy, resulting in a game over."
  relative: true # To use relative path for cover image, used in hugo Page-bundles
---

## Overview
This was a single-day hackathon at my university. We participated as a group of two where I was responsible for the programming and art and level design were done by my partner. The competition lasted around 8 hours.

The theme was "the game is a lie," which provided some challenge. Eventually we decided to make a game where the enemy blinks in and out of vision, and the player must avoid the enemy for as long as possible by combining wall-jumps with the interesting level geometry.

## Features
- Enemy chases the player at all times, fading in and out of vision.
- Player uses movement and wall-jumps to avoid the enemy.
- Score is increased the longer the player lives in a round.
- Levels are loaded from image files, allowing the game to be modded.

## Challenges
The hackathon required the use of [Pygame](https://www.pygame.org/docs/), which came with its own set of challenges. Pygame required me to build and manually draw frames, manage my own game object abstraction, and build game loop logic all by hand. Combined with the limited time, this hackathon provided a unique challenge to work with lower-level engines and accommodate the limited coding ability of my teammate.

## Modability
The most interesting feature I came up with during development was the ability to mod new levels into the game. This was accomplished by loading levels from a png file at the begining of each round. A random file would be chosen, and each color corresponded to either floor, wall, or air.

To illustrate, here are four of the levels from the game:

![Four levels of the game files as described above.](/images/keepaway/levels.webp "Four levels of the game.")

This system also made it easy for my low-code partner to implement levels on the game, while I continued to work on the game logic.

## Tech Stack
- Pygame
- Python

## Video Demo

{{< video src="/images/keepaway/videodemo.mp4" >}}
