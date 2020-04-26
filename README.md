# Machine Learning - Exoplanet Exploration

Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system. 

<b> This project explores different machine learning models capable of classifying candidate exoplanets from the raw dataset. </b>

## Getting Started

I explored four different machine learning models, and each of them are contained in individual notebooks. 
* [Logistic Model](logistic_model.ipynb)
* [Random Forests Model](Forests_Model.ipynb)
* [K-nearest neighbors classifier Model](KNN_Model.ipynb)
* [Support vector machine classifier Model](SVC_model.ipynb)

### Data Cleaning and Pre-Processing
In each of the notebooks, I clean the source [data](models) to drop null values and remove the error columns. The "y" variable for machine learning is "koi_disposition", and "x" variables are the remaining columns in the dataset.

I create a stratified train test split from the data with random_state=42.

In each of the notebooks, I explore two types of scalers (standard and minmax), and observe differences in model scores. The comparison is stored in its own [notebook](Model_Comparison.ipynb).

### Prerequisites

Which libraries did I use?
Make sure the packages are up to date by running the pip install cells in the jupyter notebook.

## Reporting

* Create a README that reports a comparison of each model's performance as well as a summary about your findings and any assumptions you can make based on your model (is your model good enough to predict new exoplanets? Why or why not? What would make your model be better at predicting new exoplanets?).

Summary table here?

### Section for each model.


## Authors

* **Heain Yee** - [Hanesy](https://github.com/hanesy), [LinkedIn](https://www.linkedin.com/in/heain-yee-82105818/)

## Acknowledgments

As guided by 2019 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.