COSTINGS ANALYSIS    

This was the task I was given to do that sparked my interest in data analytics and is described in my CV.
I have redacted the original to remove all sensitive data.
64 suppliers were accessed by 420 products using extended versions of vlookup to access multiple pages of data containing up to 128000 prices.

=IFERROR(VLOOKUP(H7,INDIRECT("'"&INDEX(Supplier_List,MATCH(1,--(COUNTIF(INDIRECT("'"&Supplier_List&"'!$A$2:$s$2000"),H7)>0),0))&"'!$A$2:$s$2000"),2,FALSE),"Not Found")

The purpose was to track incoming prices to automatically update the production costs allowing checks to keep the margins profitable. 

CAMBRIDGE SPARK ASSIGNMENTS

The following assignments were completed successfully

Analysis of a Stock Price Dataset

Analysis of a Vehicle Dataset

Analysis of FTSE Data

Analysis of Coronavirus Data

Analysis of Energy Data

Analysis of Traffic Data

Analysis of a Property Dataset

Chocolate Ratings

PORTFOLIO PROJECTS

These tasks demonstrate the skills acquired written as reports

Choosing a Second Hand Car

Marketing a Treadmill

Reasons to choose Netflix
