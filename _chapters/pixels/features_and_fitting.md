---
title: Features and fitting
keywords: RANSAC,
order: 5 # Lecture number for 2020
---

In this lecture, we will introduce model fitting for line detection using the RANSAC (Random Sample Consensus) algorithm.

<a name='intro'></a>

## Lines

Straight lines characterize many objects around us. Here are few examples where line detection is useful:

**Example 1: Shape analysis**
<<image mich slide 7>>

**Example 2: Navigation**
<<image slide 4>>

<!--- **Example 3: Computing vanishing points** -->

## Model Fitting

We would like to form a higher-level succinct representation of the features in the image by grouping multiple features based on a simple model. This section focuses on lines described as one such model (i.e. line fitting) with edge points as features.

_Note:_ Edge detection is a technique that is used to identify boundaries. It does not provide information on the orientation of pixels (shape).

**Challenges**

As with any fitting problem, we ned to take into account missing information, noise, and outliers. Our solution should be able to detect the best fitting line from edge points that could have clutter and noise. It should also be able to detect lines that bridge missing evidence.

<<image slide 5>>

Least squares regression is a common technique to find a line of best fit for a dataset. However, least squares is prone to the negative effect of outliers. When dealing with images it is often the case that the number of outliers is large. A better approach is to find a set of inliers to initiate model fitting.

## Voting Scheme

We could try to fit the model by exhausitively checking all combination of features. However, this approach is inefficient with O(N<sup>2</sup>) time complexity.

Voting is a decent alternative. The idea is to have features vote for compatible models and to capture model parameters that form a majority. It turns out that this set of winning model parameters are not affected by votes from clutter and noisy features as their voting will be inconsistent with the consensus. The problem of missing observations can also be overlooked as the fitted model can span multiple fragments. In general, voting is considered to be robust to outliers and missing data.

[Hough Transform](#edge_detection) uses this voting strategy for detecting lines. Check out this video for a quick review of Hough Transform:

https://www.youtube.com/watch?v=4zHbI-fFIlI&feature=youtu.be&t=3m35s

<<image 4.6 slide 11>>

## RANSAC

**Algorithm**

**Walk-through**

**Model parameters**

**Estimate number of iterations**

**Refined RANSAC**

**Analysis**

**Summary**
