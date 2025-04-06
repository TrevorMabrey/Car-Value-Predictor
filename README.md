# Car-Value-Predictor
# User Guide
## Step 1: Go to https://colab.research.google.com/drive/1VdZxyPW7cKjoq9Yu-893fB7aF1XQhuBp?usp=sharing

## Step 2: 
Find the tab on the top left corner called “runtime” and click on it. In the dropdown, click “run all”.
	Entries at the bottom of the “Car Sales Analysis section include details about the dataset, as well as a visual explaining the correlation between significant attributes.

![data visual reference screenshot](https://github.com/TrevorMabrey/Car-Value-Predictor/blob/main/capstoneInitialData.JPG?raw=true)
![data visual reference screenshot](https://github.com/TrevorMabrey/Car-Value-Predictor/blob/main/CapstoneDataVisual.JPG?raw=true)

## Step 3:
To use the model, navigate to the bottom of the “Car Sales Price Prediction Model” section, where you will find an input form with the user able to specify the Year, Make, Body, Transmission, State, and Odometer. Year specifies the manufacture year of the car of interest. Make is the company that produced the car, for example, Honda. The body is the standardized body type representing the car’s purpose, for instance, an SUV or sedan. The state will be the state initial of where the sale will take place. Finally, the odometer is how many miles the car has accrued since manufacture. 

![UI Widget reference screenshot](https://github.com/TrevorMabrey/Car-Value-Predictor/blob/main/CapstoneUIWidget.JPG?raw=true)




## Step 4:
After making all required selections, click on the “predict selling price” button and the model will print a determined true value of the selected car.

![UI Outcome reference screenshot](https://github.com/TrevorMabrey/Car-Value-Predictor/blob/main/CapstoneUIOutcome.JPG?raw=true)

## Machine Learning
The model for predicting the selling price will use the linear regression model from Sklearn, which is a simple and widely used algorithm for predicting attributes that are continuous. A selling price is a continuous value with an unlimited number of variants, so a regression-based tool works for this application. LinearRegression will take all input variables, and try to fit them against a straight line, hence its linear definition. The closer this line gets to all the points it is reading, the more accurate the predictive algorithm will be. 
	My model will be trained using 80 percent of the data, with 20 percent reserved for evaluation. The categorical inputs will be made into columns in the table with either 1 or 0, so that the regression algorithm can correctly use them. Attributes that either were not heavily correlated with the price outcome or resulted in the program overcoming the maximum processing ability of the host platform, were dropped from the data table. To create predictions, a form will allow the user to input attributes, which will be used to create an entry with the same data frame format as the original data and the model will match this entry to a point on the regression line representing the price. 

## Validation
Validation of the model’s performance was done using the R2 score, which is a way to measure how well the regression line fits as a coefficient. R2 was used as a metric that is easier to gauge performance when adjusting the algorithm for improvements. My model’s R2 score was .6889, which is a pretty decent correlation and can be used to create useful predictions of car values

## Solution
In the proposal, it is explained that Mabrey Motors is in need of a tool to make the buying and selling process for vehicles more efficient and accurate. Using this notebook as a tool before a transaction is made allows the model to produce a fast and accurate gauge of value that a representative can see to make a well-educated buying or selling decision. If for instance, a buyer wants to trade in their 2017 Honda coupe with 100,000 miles, the salesman might have a bias to preferring imports and overpay for that trade-in, when the model will take those attributes and produce a value that might be significantly lower. This has a clear positive benefit to the revenue of Mabrey Motors. 

## Data
https://www.kaggle.com/datasets/syedanwarafridi/vehicle-sales-data?resource=download
The data for my program was sourced from kaggle.com in a collection of sales records web-scraped from dealership websites. This data is shown to be updated on a regular basis and is largely representative of the car market currently. Entries in the data contain all the information that would be necessary to determine a car’s worth, and more than enough entries to build a holistic model, at over 400,000.

## Visualizations
The first 2 visuals are found in the Car sales analysis section of the Jupyter Notebook, the first being a histogram detailing the overall contents of the dataset, to evaluate any skews or overrepresentation. It also contains a scatterplot detailing the relationship between the 2 major factors of a car’s worth and the final selling price of that car. The third visual is included after a value is predicted, comparing the price and mileage of the prediction to that of all other cars of the same make. 

# Example Business Case and Development Outline

## Project Summary
The automotive industry has many significant challenges regarding the accurate determination of the value of used vehicles. Many factors, such as mileage, condition, market trends, and demand, can have a significant effect on this value. These factors are difficult to asses when human bias is introduced into value decision-making and influence the outcome of analysis. The current method of valuation can lead to inaccurate pricing, resulting in missed opportunities, unsold inventory, and a higher bottom line. Mabrey Motors needs to be able to navigate this highly competitive and changing industry to succeed and create an advantage. As margins in car sales are usually thin, an effective solution would include minimizing the inaccuracies of these prices to maintain consistently accurate pricing. We need a tool to be able to produce an accurate value of any vehicle without the need for human analysis. 
	For deliverables, the tool itself will be a Python-based machine learning algorithm running on Jupyter notebooks. This notebook will be hosted in Google Collab to avoid the need for an in-house processing solution. We will also create a user guide and documentation detailing the process of properly using the program, to ensure the maximum benefit to the end user. This will allow Mabrey Motors to efficiently integrate the tool into its standard workflow. The user guide will contain a step-by-step guide on accessing, configuring, and running the Python code from start to finish. 
	The benefits to this organization possessing such a tool are clear. The implementation of machine learning as a means for value analysis will remove human bias from the decision-making process, leading to more accurate and consistent outcomes. It will also produce these pricing decisions much faster than a human is capable of, greatly increasing business frequency, and therefore profit. The machine learning tool will assist Mabrey Motors reduce its unsold inventory, avoid overpaying on trade-in vehicles, and increase margins by identifying the best opportunities available on a broader scale. 
## Data Summary
The data required for training and evaluating the machine learning model will be sourced from publicly available vehicle sales transactions, which have been collected into a CSV file and hosted on Kaggle.com. The sales data, containing information about the condition, mileage, make and model, and other useful attributes is contained as a single entry in this CSV list. 
	The raw data will then be pre-processed. Entries that have incomplete attributes will be removed, as they will negatively influence the correlations that the model is trying to create. Attributes such as seller, interior color, exterior color, and vin will be dropped from the list, as they do not highly correlate to the vehicle’s value. Mmr will be dropped as it is a signifier of value, but one that uses other methods of analysis and would not allow the accurate evaluation of the model. Model will also be dropped, due to the exponentially increasing computing power when needing to vectorize so many options. The make, body type, transmission type, and state will need to be vectorized so that the model can properly correlate their values to other attributes and determine the selling price. 
	Once imported by the notebook, the data will be stored on the Google Cloud as part of the collab session, eliminating the need for physical or on-site storage. When a session ends, the data is offloaded from the project space. This process will be automatic, without needing to manually import files. 
	The data is the most important part of this tool. Access to updated and accurate information is what allows the model to produce accurate predictions. It will learn from patterns in the entries to be able to find exactly how much each affects a final value. Luckily, this data is also publicly available and not protected by any legal or cultural opposition to its collection. All entries are in no way tied to individuals and thus, no ethical issues regarding its use are to be expected. 
## Implementation
The development of this tool will follow an agile development methodology. This will utilize continuous iteration and feedback, as that feedback becomes useful features to build out or improve upon. Using Agile, the development team will be able to stay flexible, as the specific uses of the tool shift, and new purposes are discovered. Deliverables include the data analysis to produce visualizations and discover trends in the data, the prediction model, including a user interface, and the user guide for navigating the complete program. Analysis and the model will be written in Python, inside a Jupyter Notebooks session, And the model will be created using Sklearns linear regression. First, the data will be imported and pre-processed so that it can be read by the model. Then, the data will be split into a training set and testing set, for later evaluation of the model’s accuracy. After the model is created, it will be tested against the test set and given an R2 score to determine its accuracy. The UI will then be designed, with entries to create a list that will predict the selling price attribute. Testing will include unit tests at each step to ensure that information is correctly passing from module to module. 
## Evaluation
Once the data is imported and processed into a machine-readable format, data(), data.collumns, and data.describe will be able to show whether it has been read as intended and can be used in the model. After this, the visualizations for data correlation can be made to ensure they are working correctly. Verifying that the model functions will be after the evaluation function is created, and the whole unit can be run. Finally, Evaluating the effectiveness of the model will include the calculation of the R2 score on the actual vs predicted selling prices in the test set. 




