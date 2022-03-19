#Stock Market Analysis

##Using VBA to explore stock data
---
##Purpose
Steve works in finance and is searching for some specific information on stocks for his parents.  They are looking to invest in the stock market, and would like to know more about the total volume and yearly returns for the stock data that Steve has available.  In order to help Steve, we are searching an Excel workbook with stock data from the years 2017 and 2018.  This workbook has about 3000 rows of data for 12 stocks in both the 2017 and 2018 worksheets.  That is a considerable amount of data for analysis, so VBA was used to search our 2017 and 2018 worksheets for relevant financial data.  The original code created to accomplish this goal utilized a nested "for loop", which loops through all rows of data as well as a list of stock tickers.  This code runs fairly quickly for 12 stocks, but Steve would like to look at a much larger cross-section of the stock market for future analyses.  If our data set consisted of 40,000 rows instead of 3,000 the current code may take much longer to run.  Therefore, the challenge here was to re-factor our current code to only utilize one loop searching through data rows instead of looping through data rows and our list of stock tickers. 
---
##Methods
In order to utilize one loop that could capture all data for a stock ticker at once, there must be a way to reference which stock ticker is currently being searched for in the data.  This was addressed by creating a reference variable called tickerIndex with the code `tickerIndex = 0`.   This new variable was set to 0 since our tickers array begins at 0.  Additionally, three output arrays were created to hold the total volume, starting price, and ending price for each of the 12 stocks in our tickers array.  This was done using the code 
``` 
Dim tickerVolumes(12) As Long
Dim tickerStartingPrices(12) As Single
Dim tickerEndingPrices(12) As Single  
```
One more task that had to be accomplished before looping through the rows of data was setting all items of the totalVolumes output array to 0. 
```
For i = tickerArrayStart To tickerArrayEnd
        
    tickerVolumes(i) = 0
        
Next i
```
 
---
##Results
A detailed VBA subroutine was written for Steve 
