# Lab 8 – How a Neural Network Learns

## Objective

The objective of this lab is to understand how neural networks learn by making predictions, receiving feedback, and adjusting weights.

## Step 1 – Neural Network Diagram

```text
Input Layer           Middle Layer           Output Layer

Food --------\
              \
Service -------> [Decision Node] --------> LIKE / DISLIKE
              /
Price -------/
```

The network uses three inputs: Food, Service, and Price. Each input has a weight that represents its importance in making a decision.

## Step 2 – Roles

I completed this lab as an individual simulation.

- **Input Feeder:** Reads the restaurant scenarios.
- **Decision Node:** Predicts whether the customer likes or dislikes the restaurant.
- **Observer/Tracker:** Checks predictions and updates the weights.

## Part A – Training Phase

### Initial Weights

| Feature | Weight |
|---|---|
| Food | 1 |
| Service | 1 |
| Price | 1 |

All features start with equal weights.

### Training Results

The following table demonstrates an example training simulation. Predictions are illustrative rather than recorded results from a live group activity.

| Card | Food | Service | Price | Prediction | Actual | Result |
|---|---|---|---|---|---|---|
| 1 | Great | Poor | Cheap | DISLIKE | LIKE | Incorrect |
| 2 | Bad | Great | Expensive | LIKE | DISLIKE | Incorrect |
| 3 | Good | Okay | Moderate | LIKE | LIKE | Correct |
| 4 | Poor | Poor | Cheap | DISLIKE | DISLIKE | Correct |
| 5 | Excellent | Excellent | Expensive | LIKE | LIKE | Correct |
| 6 | Okay | Bad | Moderate | DISLIKE | DISLIKE | Correct |
| 7 | Great | Okay | Cheap | LIKE | LIKE | Correct |
| 8 | Poor | Excellent | Expensive | DISLIKE | DISLIKE | Correct |
| 9 | Excellent | Poor | Moderate | LIKE | LIKE | Correct |
| 10 | Okay | Okay | Expensive | DISLIKE | DISLIKE | Correct |

### Weight Adjustment Tracker

After an incorrect prediction, the feature weights are adjusted to improve future predictions.

| Stage | Food | Service | Price | Explanation |
|---|---|---|---|---|
| Initial | 1 | 1 | 1 | Equal importance |
| After Card 1 | 2 | 1 | 1 | Increased Food weight because great food resulted in LIKE |
| After Card 2 | 3 | 1 | 1 | Increased Food weight because bad food resulted in DISLIKE |
| After Card 3–10 | 3 | 1 | 1 | No further changes needed |

Food became the most important feature.

### Training Accuracy

- First 2 predictions: 0/2 correct (0%)
- Remaining 8 predictions: 8/8 correct (100%)
- Overall training accuracy: 8/10 (80%)

The example demonstrates how adjusting weights can improve prediction accuracy.

## Part B – Testing Phase

The learned weights are applied to three new restaurant scenarios.

### Final Weights

| Feature | Weight |
|---|---|
| Food | 3 |
| Service | 1 |
| Price | 1 |

### Testing Results

| Card | Food | Service | Price | Prediction | Actual | Result |
|---|---|---|---|---|---|---|
| 11 | Good | Excellent | Cheap | LIKE | LIKE | Correct |
| 12 | Bad | Bad | Expensive | DISLIKE | DISLIKE | Correct |
| 13 | Excellent | Great | Moderate | LIKE | LIKE | Correct |

**Testing Accuracy: 3/3 = 100%**

The example model correctly predicted all three new scenarios.

### Team Comparison

Since this lab was completed individually, I compared the early predictions with the later predictions instead of comparing different teams.

- Early training accuracy: 0%
- Later training accuracy: 100%
- Testing accuracy: 100%

The most important feature was Food because it had the strongest relationship with the customer's opinion in the provided scenarios.

## Reflection Questions

### 1. How did your predictions improve?

In the example simulation, the first two predictions were incorrect. After adjusting the weights, the remaining predictions were correct. This shows how feedback can help a model improve.

### 2. How did weights (tokens) help you learn?

Weights helped identify which features were more important. Food received more weight because it was the strongest indicator of whether the customer liked or disliked the restaurant.

### 3. What would happen with more layers or inputs?

More layers and inputs could help a neural network recognize more complex patterns. For example, adding restaurant cleanliness, location, and waiting time could help the model make more detailed predictions. However, a larger network may also require more training data.

### 4. How does this reflect how real AI works?

Real neural networks use training data to make predictions and compare them with expected results. They adjust their weights to reduce errors. This simulation demonstrates the basic idea, although real neural networks use mathematical calculations and optimization algorithms instead of manually adding tokens.

## Conclusion

This lab helped me understand how neural networks use inputs, weights, predictions, and feedback. The example simulation showed that increasing the importance of relevant features can improve prediction accuracy.

The most important feature in this dataset was Food, and the final testing accuracy was 100%.
