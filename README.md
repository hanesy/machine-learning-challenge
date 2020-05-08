# Machine Learning - Exoplanet Exploration
<b> This project explores different machine learning models capable of classifying candidate exoplanets from the raw dataset. </b>

Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system. 

## Research Questions
**Which machine learning model best fits the data?**

## Getting Started

I explored four different machine learning models, and each of them are contained in individual notebooks. 
* [Logistic Model](logistic_model.ipynb)
* [Random Forest Classifer Model](Forests_Model.ipynb)
* [Support vector machine classifier Model](SVC_model.ipynb)
* [K-nearest neighbors classifier Model](KNN_Model.ipynb)

**The comparative summary of the hyper-tuned models is in its own [NOTEBOOK](Model_Comparison.ipynb).**

### Prerequisites

The libraries I used are as follows:
* sklearn
* joblib
* numpy
* pandas
* matplotlib

All notebooks contain a pip install cells for joblib and sklearn that can be uncommented to make sure the version on your machine is up to date.

## Data Cleaning and Modeling
### Data Cleaning
In each of the notebooks, I clean the source [data](data) to drop null values and remove the error columns. 

### Developing the model (Pre-process, train, test)
The "y" variable for machine learning is "koi_disposition," which classifies each candidate as "confirmed", "candidate", or "false positive."  

The "x" variables are the remaining columns in the dataset. The definitions of the columns are provided at the end of each model notebook, or it can be obtained at [Kaggle](https://www.kaggle.com/nasa/kepler-exoplanet-search-results) or the [data dictionary](https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html).

From the cleaned dataframe, I create a stratified train test split from the data with random_state=42.

I scale the data using a quantile transformer and normalizer. 

I train and test the model, then hypertune them.

### Comparison
As a final step, I compile the scores and classification reports for the hypertuned models and observe the best-fit model in this [notebook](Model_Comparison.ipynb). 

## Which model best fits the data?
hypertuned rfc (random forest classifer) with standard scaler has the best fit to the data from observing the model score (0.89). Classification report of this model also has the best precision of outcomes (.80 for "CONFIRMED").

Hypertuning seems to have little impact on model scores. 

See the details in the sections below.

### Details for Each Model
The following sections show the overall scores for hypertuned and non-hypertuned models and precision for outcomes for ONLY hypertuned models. 

For details on the hypertuned models' classification reports (including recall, f-1 score, etc.), see [Model_Comparison](Model_Comparison.ipynb) notebook. 
For classification reports of the non-hypertuned models, please see each individual notebook.

---

#### [Logistic Model](logistic_model.ipynb)
**Test Scores**
| Logistic - Type | Accuracy Scores |
| ----------- | -----------: |
| Non-hypertuned | 0.87 |
| Hypertuned | 0.89 |

**Hypertuned Model Outcome Precision**
| Outcome | Precision Scores |
| ----------- | -----------: |
| CANDIDATE | 0.82 | 
| CONFIRMED | 0.76 | 
| FALSE POSITIVE | 0.99 | 
---

#### [Random Forest Classifer Model](Forests_Model.ipynb)
**Test Scores**
| RFC - Type | Accuracy Scores | 
| ----------- | -----------: |
| Non-hypertuned | 0.90 |
| Hypertuned | 0.90 | 

#### Hypertuned Model Outcome Precision
| Outcome | Precision Scores |
| ----------- | -----------: |
| CANDIDATE | 0.86 | 
| CONFIRMED | 0.80 | 
| FALSE POSITIVE | 0.97 | 
---

#### [Support vector machine classifier Model](SVC_model.ipynb)
**Test Scores**
| SVC - Type | Accuracy Scores | 
| ----------- | -----------: |
| Non-hypertuned | 0.89 | 
| Hypertuned | 0.88 | 

**Hypertuned Model Outcome Precision**
| Outcome | Precision Scores | 
| ----------- | -----------: |
| CANDIDATE | 0.80 |
| CONFIRMED | 0.76 | 
| FALSE POSITIVE | 0.99 | 
---

#### [K-nearest neighbors classifier Model](KNN_Model.ipynb)
**Test Scores**
| KNN - Type | Accuracy Scores | 
| ----------- | -----------: |
| Non-hypertuned | 0.89 | 
| Hypertuned | 0.89 | 

**Hypertuned Model Outcome Precision**
| Outcome | Precision Scores | 
| ----------- | -----------: |
| CANDIDATE | 0.86 | 
| CONFIRMED | 0.75 |
| FALSE POSITIVE | 0.99 | 


## Author

* **Heain Yee** - [Github](https://github.com/hanesy), [LinkedIn](https://www.linkedin.com/in/heain-yee-82105818/)