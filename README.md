# Custom Neural Network-Driven Self-Driving Vehicle 

A browser-based self-driving car simulation written in **pure JavaScript**.  
Uses ray-casting sensors, a custom neural network, and a genetic algorithm to train cars to navigate and avoid collisions.


## Table of Contents

- [Overview](#overview)  
- [Features](#features)  
- [How It Works](#how-it-works)  
- [Installation & Usage](#installation--usage)  
- [Architecture](#architecture)  
- [Training & Mutation](#training--mutation)  
- [Mock Images](#mock-images)  
- [Tech Stack](#tech-stack)  
- [Future Ideas](#future-ideas)  


## Overview

This simulation demonstrates how a self-driving car can be trained from scratch using only JavaScript — no external ML libraries. Cars use **ray-casting sensors** to perceive their environment and a **neural network** to decide steering, acceleration, and braking. The most successful cars evolve over generations using a **genetic algorithm**.


## Features

- Simulated car physics: velocity, steering, acceleration, collision detection  
- Ray-casting “sensors” to detect track boundaries and obstacles  
- A lightweight *feed-forward neural network* controlling each car  
- Genetic algorithm for evolving driving behavior across generations  
- Visualization of sensor rays, neural network activations, and the best “brain” in real time  
- Multiple cars: observe competition between generations


## How It Works

1. **Sense**: Each car shoots out a fixed number of “rays” in different directions. When these rays hit boundaries, the distance data is used as input.  
2. **Decide**: A neural network (with input neurons = ray count, hidden layer, and output neurons for controls) processes the sensor inputs and outputs control signals (steer left/right, accelerate, brake).  
3. **Act**: The car moves based on the neural network’s output and its current physics state.  
4. **Evolve**: After each “generation,” the best-performing cars are selected and mutated (via genetic algorithm) to create the next generation.


## Installation & Usage

1. **Clone this repo**

   ```bash
   git clone https://github.com/rabbikazmi/self-driving-vehicle.git
   cd self-driving-vehicle

2. **Open index.html**
Simply open the index.html file in your browser to run the simulation.

Watch the best car’s brain and sensor rays in real-time

## Architecture

### Core Modules

index.html – Main canvas layout and UI container.

styles.css – Styling for the simulation interface.

### Vehicle & Control System

car.js – Car physics, movement, collision detection, and AI decision handling.

control.js – Manual controls (keyboard) + AI control routing.

car.png – Car sprite used for rendering.

### Autonomous Intelligence

network.js – Lightweight neural network (5→6→4 architecture), mutation logic, and feed-forward inference.

utils.js – Helper utilities including lerp() and randomization functions.

### Environment & Perception

road.js – Road layout, lane generation, and environment boundaries.

sensor.js – Ray-casting based LIDAR-like sensor system for detecting traffic & walls.

### Simulation Engine

main.js – Entry point: spawns cars, traffic, rendering loop, and model evolution logic.

visualizer.js – Neural network visual debugger (weights, activations, layer connections).


## Training & Mutation

- The genetic algorithm applies small random changes (mutations) to network weights and biases each generation

- “Brains” (neural networks) from the previous generation carry over, ensuring better-performing models are retained and improved

You can tune:

### Mutation intensity

- Number of “elite” cars carried over

- Population size

- Number of generations

## Mock Images



## Tech Stack

1. JavaScript (ES6+)

2. HTML5 Canvas

3. Custom Neural Network (no external ML libraries)

4. Genetic Algorithm

5. Ray-Casting Sensors

## Future Ideas

- Add multi-agent traffic: simulate multiple autonomous cars on the same track

- Introduce dynamic obstacles or changing track layouts

- Save and load “brains” (trained neural networks) from local storage / files

- Add reinforcement learning instead of GA for training

- Introduce sensor noise and more realistic physics
