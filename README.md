# PricePoint Technical Report

## Data Acquistions

The data utilized for this project came from the Metropolitan Regional Information System. The data warehouse contains a record for every piece of property sold in the states of Washington, D.C., Virgina, Maryland, Delaware, and Pennsylvania since 1998. 

The data warehouse contains millions of rows and 351 features for every row. Because this project was isolated to the Washington, D.C. area it limited the data to approx 200K rows. Being able to predict prices and examine driving feature futher reduced the sample to recent history. Two years was choosen as a marker and provided a sample size of 17K.

The data was provided by a local real estate brokerage in a CSV format, because of system limitations of 5K per query. The limitation nessecitated three seperate pools to aggregate the data and combining the tables via Microsoft Excel.

## Data Cleaning, Transforming, and Pre-Processing



