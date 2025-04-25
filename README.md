# PMA-flight_deley_prediction



## Overview

This project provides a simplified approach to predicting flight delays using IBM SPSS Modeler. It focuses on demonstrating a basic workflow for data preparation, a single predictive model, and preliminary insights into factors influencing flight delays. This serves as an introductory example for leveraging SPSS Modeler for flight delay analysis.

## Table of Contents

* [FLIGHT_DELEY_PREDICTION](#problem-statement)
* [Dataset](#dataset)
* [Data Preparation in SPSS Modeler](#data-preparation-in-spss-modeler)
* [Basic Feature Selection](#basic-feature-selection)
* [Building a Simple Predictive Model in SPSS Modeler](#building-a-simple-predictive-model-in-spss-modeler)
* [Evaluating the Model](#evaluating-the-model)
* [Preliminary Insights](#preliminary-insights)
* [Software Used](#software-used)
* [Project Files](#project-files)

## Problem Statement

This project aims to build a basic predictive model in IBM SPSS Modeler to determine whether a flight will be delayed based on a limited set of readily available features. The goal is to illustrate a fundamental prediction process rather than achieving high accuracy with complex modeling.

## Dataset

For this simple project, we will consider a subset of historical flight data including:

* Airline carrier
* Origin airport
* Destination airport
* Scheduled departure time (hour of the day)
* Day of the week
* Arrival delay (our target variable - whether it's > 15 minutes, for example)

**[Optional: Briefly mention a potential source for such data, even if it's a sample dataset you've created or a pointer to a larger public dataset.]**

## Data Preparation in SPSS Modeler

The initial steps in SPSS Modeler involve:

1.  **Importing Data:** Using the Source node (e.g., CSV Input) to bring the flight data into the stream.
2.  **Defining Data Types:** Utilizing the Type node to ensure the correct data types for each field (e.g., Nominal for airlines and airports, Numeric for time).
3.  **Handling Missing Values (Simple Approach):** Using the Filter node to remove rows with missing values in the key predictive features and the target variable for simplicity.

## Basic Feature Selection

For this simple model, we will select a few key features that are intuitively likely to influence delays:

* **Airline Carrier:** Different airlines might have varying operational efficiencies.
* **Origin Airport:** Some airports might experience more congestion than others.
* **Scheduled Departure Hour:** Flights during peak hours might be more prone to delays.
* **Day of the Week:** Weekday vs. weekend traffic could impact delays.

We will use the Filter node to keep only these selected input features and the target variable (e.g., a binary flag indicating if arrival delay was greater than 15 minutes, derived using a Derive node).

## Building a Simple Predictive Model in SPSS Modeler

We will use a basic classification model available in SPSS Modeler:

* **Decision Tree (CHAID or C5.0):** This model is relatively easy to interpret and can identify simple rules based on the selected features to predict flight delays.

To build the model:

1.  Drag and drop a Partition node to split the data into training and testing sets (e.g., 70% training, 30% testing).
2.  Drag and drop a Decision Tree modeling node (e.g., CHAID) and connect the training partition to it.
3.  Configure the Decision Tree node, specifying the target variable (the binary delay indicator) and the input features (airline, origin, departure hour, day of week). Use default or simple settings for the tree growth.
4.  Run the Decision Tree node to build the model.

## Evaluating the Model

To assess the basic performance of our simple model:

1.  Drag and drop an Evaluation node and connect the testing partition and the Decision Tree model nugget to it.
2.  Run the Evaluation node.
3.  Examine the output, focusing on the **accuracy** (overall percentage of correct predictions) and the **confusion matrix** to see how well the model predicts delayed and non-delayed flights.

**[Example of a simple interpretation: "The decision tree model correctly predicted whether a flight would be delayed approximately XX% of the time on the test data."]**

## Preliminary Insights

Even with a simple model, we might gain some initial insights:

* **[Example Insight 1: e.g., A specific airline in our data shows a slightly higher proportion of delayed flights according to the tree rules.]**
* **[Example Insight 2: e.g., Flights departing during a particular hour of the day from a specific airport appear more likely to be delayed in the tree structure.]**

**[Consider including a screenshot of a simple Decision Tree output or the Evaluation node results.]**

## Software Used

* **IBM SPSS Modeler:** Version [Specify Version if applicable]

## Project Files

* **[Name of your simple SPSS Modeler Stream File] (.str):** This file contains the basic stream created for this project.

This simplified example provides a starting point for flight delay prediction using IBM SPSS Modeler, focusing on fundamental steps and a single, interpretable model. You can build upon this by incorporating more features, exploring different models, and refining the data preparation steps for more accurate predictions in a more complex project. Remember to replace the bracketed placeholders with your specific project details and file names.
