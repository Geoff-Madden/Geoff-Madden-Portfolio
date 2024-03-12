COSTINGS ANALYSIS    

This was the task I was given to do that sparked my interest in data analytics and is described in my CV.
I have redacted to original to remove all the sensitive data.
64 suppliers prices were accessed by 420 products using a version of vlookup to access multiple pages of data.

=IFERROR(VLOOKUP(H7,INDIRECT("'"&INDEX(Supplier_List,MATCH(1,--(COUNTIF(INDIRECT("'"&Supplier_List&"'!$A$2:$s$2000"),H7)>0),0))&"'!$A$2:$s$2000"),2,FALSE),"Not Found")

The purpose was to track incoming prices to update the production costs and keep the margins profitable. 

ANALYSIS OF A STOCK PRICE DATASET

Import files into Pandas
Examine dataframes using df.head(), df.sample(8), df.info(), df.shape
Get basic statistics with df.describe()
Sorting and filtering data
Retrieving data using index, iloc, loc
Updating values and adding columns

ANALYSIS OF A VEHICLE DATASET



ANALYSIS OF FTSE DATA

ANALYSIS OF CORONAVIRUS DATA

ANALYSIS OF ENERGY DATA

ANALYSIS OF TRAFFIC DATA

ANALYSIS OF A PROPERTY DATASET

CHOCOLATE RATINGS
