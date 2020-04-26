# Machine Learning - Exoplanet Exploration
<b> This project explores different machine learning models capable of classifying candidate exoplanets from the raw dataset. </b>

Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system. 

## Research Questions
Overall, I was interested in answering the question:

**Which machine learning model best fits the data?**

I also had a couple smaller curiosities I wanted to learn from each of the models.
* What is the difference between using standard scaler and minmax scaler, if any?
* What is the improvement from hypertuning the model, if any?

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

### Pre-Processing
The "y" variable for machine learning is "koi_disposition," which classifies each candidate as "confirmed", "candidate", or "false positive."  

The "x" variables are the remaining columns in the dataset. The definitions of the columns are provided at the end of each model notebook, or it can be obtained at [Kaggle](https://www.kaggle.com/nasa/kepler-exoplanet-search-results) or the [data dictionary](https://exoplanetarchive.ipac.caltech.edu/docs/API_kepcandidate_columns.html).

From the cleaned dataframe, I create a stratified train test split from the data with random_state=42.

I scale the data ("x" variables) and train the model.

### Modeling
1. For each model, I train the model with two types of scalers (standard and min max), and observe the difference in scores.
2. I also observe how much the model improves by hypertuning by some parameters. 
(Sidenote: It would be interesting to note how much the best scores changes by tuning it to differently defined parameters, but is beyond the scope of this project.)

The hypertuned models are saved and stored in this [folder](models).

### Comparison
As a final step, I compile the scores and classification reports for the hypertuned models and observe the best-fit model in this [notebook](Model_Comparison.ipynb). 

## Research Answers
**As mentioned in the beginning of this README, I had 3 research questions.**
1. Which model best fits the data?
2. What is the difference between using standard scaler and minmax scaler, if any?
3. What is the improvement from hypertuning the model?

**Answers**
1. In conclusion, hypertuned rfc (random forest classifer) with standard scaler has the best fit to the data from observing the model score (0.91). Classification report of this model also has the best precision of outcomes.
2. There was a difference between using a standard or minmax scaler, but the difference was not very big. 
3. Most models showed improvement from hypertuning. 

See the details in the sections below.

### Details for Each Model
The following sections show the overall scores for hypertuned and non-hypertuned models and precision for outcomes for ONLY hypertuned models. 

For details on the hypertuned models' classification reports (including recall, f-1 score, etc.), see [Model_Comparison](Model_Comparison.ipynb) notebook. 
For classification reports of the non-hypertuned models, please see each individual notebook.

---

#### [Logistic Model](logistic_model.ipynb)
**Test Scores**
| Logistic | MinMax Scaler | Standard Scaler |
| ----------- | -----------: |-----------: |
| Non-hypertuned | 0.816 | 0.829 |
| Hypertuned | 0.828 | 0.834 |

**Hypertuned Model Outcome Precision**
| Logistic | MinMax Scaler | Standard Scaler |
| ----------- | -----------: |-----------: |
| CANDIDATE | 0.68 | 0.69 |
| CONFIRMED | 0.66 | 0.66 |
| FALSE POSITIVE | 0.99 | 0.99 |
---

#### [Random Forest Classifer Model](Forests_Model.ipynb)
**Test Scores**
| RFC | MinMax Scaler | Standard Scaler |
| ----------- | -----------: |-----------: |
| Non-hypertuned | 0.907 | 0.908 |
| Hypertuned | 0.904 | 0.906 |

#### Hypertuned Model Outcome Precision
| RFC | MinMax Scaler | Standard Scaler |
| ----------- | -----------: |-----------: |
| CANDIDATE | 0.84 | 0.84 |
| CONFIRMED | 0.81 | 0.81 |
| FALSE POSITIVE | 0.98 | 0.98 |
---

#### [Support vector machine classifier Model](SVC_model.ipynb)
**Test Scores**
| SVC | MinMax Scaler | Standard Scaler |
| ----------- | -----------: |-----------: |
| Non-hypertuned | 0.812 | 0.824 |
| Hypertuned | 0.802 | 0.832 |

**Hypertuned Model Outcome Precision**
| SVC | MinMax Scaler | Standard Scaler |
| ----------- | -----------: |-----------: |
| CANDIDATE | 0.66 | 0.70 |
| CONFIRMED | 0.59 | 0.66 |
| FALSE POSITIVE | 0.99 | 0.99 |
---

#### [K-nearest neighbors classifier Model](KNN_Model.ipynb)
**Test Scores**
| KNN | MinMax Scaler | Standard Scaler |
| ----------- | -----------: |-----------: |
| Non-hypertuned | 0.791 | 0.804 |
| Hypertuned | 0.795 | 0.815 |

**Hypertuned Model Outcome Precision**
| KNN | MinMax Scaler | Standard Scaler |
| ----------- | -----------: |-----------: |
| CANDIDATE | 0.62 | 0.66 |
| CONFIRMED | 0.59 | 0.63 |
| FALSE POSITIVE | 0.99 | 0.98 |


## Authors

* **Heain Yee** - [Github](https://github.com/hanesy), [LinkedIn](https://www.linkedin.com/in/heain-yee-82105818/)