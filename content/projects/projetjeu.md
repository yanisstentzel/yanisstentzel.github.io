---
title: "Brick Breaker Game"
description: "Development of a classic arcade game using Vanilla JS, HTML5 Canvas, and CSS3."
date: 2025-12-10
tags: ["JavaScript", "HTML5 Canvas", "CSS3", "Web Development"]
categories: ["Academic Projects"]
weight: 2
showToc: true
TocOpen: false

cover:
    image: "/projects/cassebrique.png#center"
    alt: "Screenshot of the app"
    relative: true 
---

## Context
This project was entirely developed as part of the **R3.03 Web Technologies** module during my second year of the Bachelor of Technology (BUT) in Data Science. The goal was to design an interactive, smooth, and accessible web application directly in the browser, relying solely on web standards without using any external frameworks or game engines.

➔ **[View the complete repository on GitHub](https://github.com/yanisstentzel/academicprojects/tree/main/Programming/ProjetJeu)**

![Brick Breaker Game Preview](/projects/cassebrique.png)

## Key Features
The project revisits the classic brick breaker with a clean design and responsive game mechanics:
- **Dynamic Controls:** The paddle accurately tracks horizontal mouse movements for optimal gameplay.
- **Progression System:** Real-time score management, updated with every destroyed brick.
- **Local Saving:** Implementation of a persistent High Score system across sessions using the browser's `localStorage` API.
- **Overlay Interface:** Start menu and "sudden death" management (if the ball hits the bottom) integrated directly over the canvas via CSS, preventing unnecessary page reloads.

## Technologies Used
- **HTML5 & Canvas API:** Page structuring and use of the `<canvas>` tag as a 2D rendering area (drawing the ball, paddle, and brick matrix).
- **CSS3:** Global layout using Flexbox, UI/UX design (buttons, typography), and display state management for start and game over screens.
- **Vanilla JavaScript:** 
  - Creation of the game engine based on the `requestAnimationFrame` method to ensure smooth animation.
  - Development of algorithmic collision logic (AABB) between the ball, screen borders, paddle, and destructible elements.
  - DOM event manipulation (mouse movements, clicks).

## Code Snippet: Data Persistence
One of the interesting aspects of this project was integrating client-side high score saving in a very simple yet effective way:

```javascript
// Retrieve the saved high score on page load (or 0 if none exists)
let highScore = localStorage.getItem("bestScore") || 0;
highScoreSpan.innerText = highScore;

// Later, check at the end of the game:
if (score > highScore) {
    highScore = score;
    localStorage.setItem("bestScore", highScore); // Save the new record
    alert("NEW RECORD! You won!");
}