# PricePoint Technical Report

## Overview

The purpose of PricePoint is to determine the most revenue made based on renovations or changes made to the property in a short period of time i.e. < three years.  

## Data Acquistions

The data utilized for this project came from the Metropolitan Regional Information System. The data warehouse contains a record for every piece of property sold in the states of Washington, D.C., Virgina, Maryland, Delaware, and Pennsylvania since 1998. 

The data warehouse contains millions of rows and 351 features for every row. Because this project was isolated to the Washington, D.C. area it limited the data to approx 200K rows. Being able to predict prices and examine driving feature futher reduced the sample to recent history. Two years was choosen as a marker and provided a sample size of 17K.

The data was provided by a local real estate brokerage in a CSV format, because of system limitations of 5K per query. The limitation nessecitated three seperate pools to aggregate the data and combining the tables via Microsoft Excel.

## Data Cleaning, Transforming, and Pre-Processing

Basic data cleaning included getting rid of bad data elements by finding and eliminating obvious errors. Transformations entailed creating date/time objects, creating dummy variables as there are a plethora of categorical features in the data set, and transforming bools to ints. 

The purpose of the project is to find quick renovations made to a property that maximize revenue. Therefore the first thing that needed to be done is find duplicates in the data frame and ones within three years of each other. The next step was to subtract the features of the original duplicate from the most recent duplicate in order to find out what changed or capture the delta of the features.

## Operationalizing the Outcome Variable and Independant Variables

The project is solving a business question, which property to buy for renovation and which renovations might lead to the highest return. This project is limited in scope and only captures the revenue side at this time (exluding expenditures for lack of data). Therefore the outcome variable that makes the most sense is ClosePrice or revenue made from a transaction. 

Initial analysis focused on independant variables: square footage, number of bedrooms, number of full baths, and number of half baths. Outside of stylistic considerations these are industry standard variables for valuation. Additional analysis brought in categorical information such as the inclusion of parking or a garage and other amenitiees.

## Models and Hyperparameters

The first plotting accomplished was a scatter plot to visualize the relation of the respective variables to 'ClosePrice'. Following that a multi linear regression was used and the residuals were plotted to determine the accuracy of the model. It performing this it appeared that a large amount of 0s in the 'LivingArea' variable were skewing the results.

In Model Run #2 the data was cleaned further to reduce skewness and a MLR was run again, this time plotting the R^2. The results were found the be weak at .379. Additional analysis was done by breaking the renovations into small, medium, and large (by square foot), this showed that the model was better at predicting small and medium renovations while large renovations had greater variance. 

Lastly the decision tree was used to determine attirbutes most associated with the dependant variable 'CloseePrice'

## Future Deployment Strategies, Additional Data, and Modeling Techniques

Once brought to greater maturity this product will be utilized to make acquistion decisions with D.C. and other markets. It will be changed from a Jupyter Notebook to production code and a UI build of for use by analysts and acquistion managers. 

There are a plethora of additional data sources to include. From the existing dataset making better use of the categories or features concerning amenties. The data warehouse also includes a total of 351 attributes per property, more features could be brought in by running additional queries. Finally since this is an acquistion decision support tool, costs also play a major roll in the decisions being made. Therefore the cost side will be another large piece of the project to be incorporated

In the future there are many different types of analysis to be done to help develop the product further. One is NLP in order to better capture the amenities or changes in amenities that area provided. Computer vision could also be used to determine the condition of the property beyond what is include in the attributes of the system. Other advanced methods of classisifaction could also be used to better classify the outputs and assist the decision making process







