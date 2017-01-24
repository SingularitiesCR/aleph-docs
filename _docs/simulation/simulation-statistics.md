---
title: Simulation Statistics
category: Simulation
order: 2
---
The simulation returns a series of statistics that measure it's performance. They can be used for tuning, testing new datasets or adjusting specific parameters.

## Hits
  
During the intra-visit stage, when the belief system believes one of the items in a transaction it's called a hit. Several statistics measure hits in different places. The amount of hits usually goes up as the belief system learns more and more about the dataset. **Average Hits** measures the average hits for every transaction in the dataset.  **Initial Hits** and **Final Hits** measure the percentage of hits in the Pre-Visit and Post-Visit stages of the simulation.

## Jaccard
  
The [Jaccard Index](https://en.wikipedia.org/wiki/Jaccard_index) compares the similarities between two sets. It's used to compare belief systems and transactions with each other. 

## Fitness
  
The fitness is the jaccard index of the transaction in progress with the current belief system. It's a number from 0 to 1. The closer it gets to 1, the closer the Belief System's prediction is to the transaction.