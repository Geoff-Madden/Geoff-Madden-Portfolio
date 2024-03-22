COSTINGS ANALYSIS    

This was the task I was given to do that sparked my interest in data analytics and is described in my CV.
I have redacted the original to remove all sensitive data.
64 suppliers were accessed by 420 products using extended versions of vlookup to access multiple pages of data containing up to 128000 prices.

=IFERROR(VLOOKUP(H7,INDIRECT("'"&INDEX(Supplier_List,MATCH(1,--(COUNTIF(INDIRECT("'"&Supplier_List&"'!$A$2:$s$2000"),H7)>0),0))&"'!$A$2:$s$2000"),2,FALSE),"Not Found")

The purpose was to track incoming prices to automatically update the production costs allowing checks to keep the margins profitable. 

CAMBRIDGE SPARK ASSIGNMENTS

The following assignments were completed successfully

ANALYSIS OF A STOCK PRICE DATASET

ANALYSIS OF A VEHICLE DATASET

ANALYSIS OF FTSE DATA

ANALYSIS OF CORONAVIRUS DATA

ANALYSIS OF ENERGY DATA

ANALYSIS OF TRAFFIC DATA

ANALYSIS OF A PROPERTY DATASET

CHOCOLATE RATINGS


PORTFOLIO PROJECTS

These tasks demonstrate the skills acquired written as reports
