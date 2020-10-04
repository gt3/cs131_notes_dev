---
title: Features and fitting
keywords: RANSAC,
order: 5 # Lecture number for 2020
---

In this lecture, we will introduce model fitting for line detection using the RANSAC (Random Sample Consensus) algorithm.

<a name='intro'></a>

## Line Fitting

Straight lines characterize many objects around us. Here are few examples where line fitting is used:

**Example 1: Shape analysis**
<<image mich slide 7>>

**Example 2: Navigation**
<<image slide 4>>

<!--- **Example 3: Computing vanishing points** -->

_Note:_ Edge detection is a technique that is used to identify boundaries. It does not provide information on the orientation of pixels.

**Challenges**

As with any fitting problem, we ned to take into account missing information, noise, and outliers. Our solution should be able to able to detect the best fitting line from the given edge points despite any clutter or noise. It should also be able to detect lines that bridge missing evidence.

<<image slide 5>>

## Model Fitting

We would like to form a higher-level succinct representation of the features in the image by grouping multiple features based on a simple model. This section focuses on lines described as one such simple model that relies on edge points as  features.

Least squares regression is a common technique to find a line of best fit for a dataset. However, least squares is prone to the negative effect of outliers on fitting. In the case of images, it is often the case that the number of outliers is large. A better approach is to find a set of inliers to initiate model fitting.


