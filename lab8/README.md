# Lab 8 – How a Neural Network Learns

## Objective
The objective of this lab is to understand how a neural network learns through predictions, feedback, and weight adjustments.

## Step 1 – Neural Network Diagram

```text
Input Layer          Decision Node         Output Layer

Food --------\
              \
Service -------> [Decision Node] -------> LIKE / DISLIKE
              /
Price -------/
```

The neural network has three inputs: Food, Service, and Price. The decision node uses these inputs and their weights to predict whether a customer likes or dislikes a restaurant.

## Step 2 – Roles

This lab was completed individually. I simulated all three roles:

- **Input Feeder:** Reads the restaurant scenarios.
- **Decision Node:** Predicts LIKE or DISLIKE.
- **Observer/Tracker:** Records predictions, checks the correct answers, and adjusts weights.

## Initial Weights

| Feature | Initial Weight |
|---|---|
| Food | 1 |
| Service | 1 |
| Price | 1 |

All features start with equal importance. The weights will change during training based on prediction errors.

