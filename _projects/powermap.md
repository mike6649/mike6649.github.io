---
layout: page
title: PowerMap
description: A tool to examine energy usage data for buildings in the US
img: assets/img/powermap.jpg
redirect: https://devpost.com/software/power-map
importance: 2
category: work
---

# Inspiration
The increasing demand for sustainable and energy-efficient buildings has created a need to predict energy consumption. Georgia Tech Infrastructure & Sustainability oversees campus buildings and focuses on improving energy efficiency, yet the sheer scale of the campus causes the need for some work to be prioritized over others. Being able to conveniently quantify the energy impact of improvements would ease this prioritization process. The first step is to let building administrators examine energy data for existing buildings.

# What it does
Our tool uses ML combined with weather and building data to make predictions on energy usage of buildings in America. Our solution can be applied to buildings of a variety of sizes, ages, and types. We believe our solution can significantly reduce the energy consumption of buildings and contribute to a more sustainable future.
How we built it

We trained a model using an ensemble regressor model with gradient boosting in scikit-learn and deployed it onto a Flask Server. Instead of decision trees which are one large and deep tree, ensemble models are made up of many small trees. These shallow trees are individually weak predictors but form an ensemble and collectively “vote” on a predicted value, forming a strong predictor. Gradient boosting refers to successively adding new trees to the model and calculating the importance of each tree such as to minimize the loss.

We used Google Maps API to embed a map interface onto our React website. Once the user searches for a building, essential building information is sent to a backend server, which automatically fetches any needed data from remote services to perform the energy prediction. Namely, we use open-meteo for grabbing weather data, and Precisely for grabbing building information.
