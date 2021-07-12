# Election-Analysis

## Overview of Election Audit
### Background
A Colorado Board of Elections employee has requested an election audit of a recent local congressional election. The audit should determine the winner of the election by popular vote. The audit should also provide more information about the voting data by calculating the total vote and each candidate's vote count along with their percentage of total votes. In addition, the employee has requested that the analysis break down the voting data by county to determine the county with the largest voter turnout.

### Purpose 
The purpose of this analysis is to deliver the election results efficiently by automating calculations with Python. By using Python, we can analyze a large data set using loops and conditional statements. While this analysis provides the results from this local congressional election, the summary also includes suggestions for modifying this script to be used in the future for any election. 

## Resources
* Data Source: election_results.csv
* Software: Python 3.9.6, Visual Studio Code 1.58.0

## Election-Audit Results
The results of the election audit were printed in the command line and written into an election results text file. The screenshots of these results are included in the following images. 

<img width="429" alt="Screen Shot 2021-07-11 at 9 58 35 PM" src="https://user-images.githubusercontent.com/85946042/125224402-2f813980-e293-11eb-8e69-c3b5be4a53ec.png"> <img width="417" alt="Screen Shot 2021-07-11 at 9 58 19 PM" src="https://user-images.githubusercontent.com/85946042/125224409-327c2a00-e293-11eb-8dd6-f40d889cdf56.png">

The analysis of the election shows that:
* There were 369,711 votes cast in the election.
* The candidates were:
  - Charles Casper Stockham
  - Diana DeGette
  - Raymon Anthony Doane
* The candidate results were:
  - Charles Casper Stockham received 23.0% of the vote and 85,213 votes.
  - Diana DeGette received 73.8% of the vote and 272,892 votes.
  - Raymon Anthony Doane received 3.1% of the vote and 11,606 votes.
* The voter turnout for each county was:
  - Jefferson County had 38,855 votes, for 10.5% of the total election turnout.
  - Denver County had 306,055 votes, for 82.8% of the total election turnout.
  - Arapahoe County had 24,801 votes, for 3.1% of the total election turnout.
* The county with the largest voter turnout was Denver County.
* The winner of the election was:
  - Diana DeGette, who received 73.8% of the cote and 272,892 votes. 

The following images show the script that counted the votes and a portion of the script that printed the results to the command line and text file. 

<img width="519" alt="Screen Shot 2021-07-11 at 9 46 29 PM" src="https://user-images.githubusercontent.com/85946042/125224859-f1384a00-e293-11eb-8b15-42f6a201fcc5.png">
<img width="372" alt="Screen Shot 2021-07-11 at 10 16 53 PM" src="https://user-images.githubusercontent.com/85946042/125225979-cf3fc700-e295-11eb-8681-58cb211725e3.png">




## Election-Audit Summary
The current election results analysis script would work for other election results spreadsheets with the same format: county and candidate name columns. It is also important that the script apply to other election results in the future. The challenge here is avoiding hard-coding, so that the script will work for data sets with more columnns or different formats. 

This script works generally to count votes and determine the winner based on popular vote and divides the data based on counties. For a city or county election, however, the user might want to break down the data by smaller areas, like districts, in which case there would be a district column instead of a county column. In this case, we could modify the script to read the headers of each column and create variables to reflect district, for instance, instead of hard-coded county variables. An organized way to do this would be to create dictionaries with variable lists created from the header column rows by using Pandas data frames. By creating dictionaries and adding the headers as variables, it would be easier to write to the text file and have appropriate results (not just for county, but for whatever region desired.) 


Another difference in format might occur in a national election, where we would want to see not only county data, but also state data. In this case, we would want to check to see if there is another column for state. We can create a conditional statement to check for a state name, and if there is a state, we can create another for loop to count votes by state with the same logic as the for loops we used to calculate votes by county, like in the image below. If the condition is not met, i.e. there is not an additional column with a region to analyze, then the script would continue outside of that conditional statement. 

<img width="709" alt="Screen Shot 2021-07-11 at 9 46 14 PM" src="https://user-images.githubusercontent.com/85946042/125224520-6a836d00-e293-11eb-9e7e-3ce9beb7698c.png">

This summary explored two modifications that would allow the user to apply this script to smaller or bigger election sizes. There may be other cases where the data format is completely different, which would require the script to be altered further. One example is a ranked-choice voting system, where the voter ranks their choices 1st, 2nd, 3rd, etc. and the script would have to weight the choices and find the candidate with the largest weighted sum to determine the winner. In this scenario, we could perform calculations for each column first; for example, the 1st ranked candidate votes would all be counted and each multiplied by the highest weight down the row. We would perform this loop for the next column vote count with a smaller multiplied weight, etc. To get the total, we would initialize a variable, create a for loop similar to those in the current script, then instead of incrementing by one, we would increment by the weighted vote in each row. At the end, we would check to see which candidate had the highest summed vote. We could also break down the percentage values for who had the greatest portion of votes in each ranking. 




