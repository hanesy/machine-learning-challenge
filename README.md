# Machine Learning - Exoplanet Exploration
<b> This project explores different machine learning models capable of classifying candidate exoplanets from the raw dataset. </b>

Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system. 

## Getting Started

I explored four different machine learning models, and each of them are contained in individual notebooks. 
* [Logistic Model](logistic_model.ipynb)
* [Random Forests Model](Forests_Model.ipynb)
* [K-nearest neighbors classifier Model](KNN_Model.ipynb)
* [Support vector machine classifier Model](SVC_model.ipynb)

The comparison of the hyper-tuned models is shown [here](Model_Comparison.ipynb).

### Prerequisites

The libraries I used are as follows:
* sklearn
* joblib
* numpy
* pandas
* warnings

All notebooks contain a pip install cells for joblib and sklearn that can be uncommented to make sure the version on your machine is up to date.

## Data Cleaning, Pre-Processing, and Modeling
### Data Cleaning
In each of the notebooks, I clean the source [data](data) to drop null values and remove the error columns. 

### Pre-Processing
The "y" variable for machine learning is "koi_disposition," which classifies each candidate as "confirmed", "candidate", or "false positive."  and "x" variables are the remaining columns in the dataset. The definitions of the columns are provided at the end of each model notebook, or it can be obtained at [Kaggle](https://www.kaggle.com/nasa/kepler-exoplanet-search-results) or the [data dictionary](https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html).

From the cleaned dataframe, I create a stratified train test split from the data with random_state=42.

### Modeling
1. For each model, I train the model with two types of scalers (standard and min max), and observe the difference in scores.
2. I also observe how much the model improves by hypertuning by some parameters. It would be interesting to note how much the best scores changes by tuning it to differently defined parameters, but is beyond the scope of this project.

The hypertuned models for the two scaler methods are stored in this [folder](models).

### Comparison
As a final step, I compile the scores for the hypertuned models and observe the best-fit model in this [notebook](Model_Comparison.ipynb). 

## Reporting

For each of the models, I asked the following questions:
* What is the difference between using standard scaler and minmax scaler, if any?
* What is the improvement 

From observing the model scores, rfc (random forest classifer) with standard scaler has the best fit to the data.

### Logistic Model
In the non-hypertuned 

### Random Forests Model
### K-Nearest Neighbors Classifier Model
### Support Vector Machine Classifier Model


* Create a README that reports a comparison of each model's performance as well as a summary about your findings and any assumptions you can make based on your model (is your model good enough to predict new exoplanets? Why or why not? What would make your model be better at predicting new exoplanets?).

Summary table here?

### Section for each model.


## Authors

* **Heain Yee** - [Hanesy](https://github.com/hanesy), [LinkedIn](https://www.linkedin.com/in/heain-yee-82105818/)

## Acknowledgments

As guided by 2019 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.