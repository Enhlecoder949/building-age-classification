# Building Age Classification

A data science project developed during the **UCT StatsGeeks Data Science Hackathon 2026**.

## Overview

The goal of this project was to use **Landsat satellite data and machine learning to predict building-age classes**.

We trained our model using data from **Madrid** and then investigated how well it could transfer to **Amsterdam**, a city with different environmental and urban characteristics.

The main question we explored was:

> Can a model trained in one city generalise to a different city using only a small amount of local labelled data?

## Data

Our dataset combines:

- **Landsat satellite measurements** across six spectral bands
- **Building construction records** used to determine building-age classes
- A **30 × 30 metre pixel grid**

Each pixel is assigned to one of **four building-age classes**.

We also used measurements collected over many years and removed readings affected by cloud or haze.

## Feature Engineering

In addition to the original Landsat bands, we created additional features from the satellite data, including:

- Spectral indices
- Vegetation-related features
- Built-up area features
- Temporal features describing changes over time

These features were used to give the model more information about the characteristics of each pixel.

## Machine Learning Approach

We used a **Random Forest classifier** to predict the four building-age classes.

The model was trained on Madrid data and evaluated using **cross-validation**.

We then tested its ability to transfer to Amsterdam using two approaches:

### Zero-shot transfer

The Madrid-trained model was applied to Amsterdam without using labelled Amsterdam data.

### Few-shot transfer

We gradually introduced labelled Amsterdam data:

- 5 pixels per class
- 25 pixels per class
- 50 pixels per class
- 100 pixels per class
- 200 pixels per class

We compared the model's performance at each level to see how additional local data affected the results.

## Evaluation

We used **macro F1-score** to evaluate performance across the four building-age classes.

This allowed us to give equal importance to each class rather than allowing the more common classes to dominate the overall score.

## Repository Contents

- `notebooks/` — notebooks used during the project
- `data/` — Madrid and Amsterdam datasets
- `preprocessed/` — preprocessed data used for modelling
- `metric_learning_approach.md` — documentation of the metric learning approach
- `written_justification.pdf` — project justification
- `final_notebook.ipynb` — final analysis and modelling workflow

## Conclusion

Our project explored whether satellite data can be used to predict building age and, more importantly, whether a model trained in one city can generalise to another.

We hope our final model performs well when tested on the new dataset provided by the hackathon organisers and that the approach can generalise beyond the cities used in our experiments.

## Hackathon

**UCT StatsGeeks Data Science Hackathon 2026**

Developed as part of the 2026 hackathon by our team.
