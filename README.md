# Personal-Dataset-Project
Personal data set project for DATA 115
Data Set: COVID-19_Reported_Patient_Impact_and_Hospital_Capacity_by_State_Timeseries
Source: www.healthdata.gov
The site is managed by the U.S. Department of Health and Human Services Office of the Chief Data Officer. 

Motivation:
The reason I wanted to look into this information was because I wanted to see just how bad COVID19 affected the US, since it affected us to the point where we couldn't go to school in person. At first I wanted to see the effects of COVID all over the world and one thing I wanted to look particularly were the deaths. But after trying to look into data for that I decided that it was to big of a topic for just one person to work on and I felt that if I really wanted to see the impact of it I would have to look at the probelm more local. So I decided to look at the impact COVID had on Washington State. 

Data Process:
The way I wanted to manipulate my data set was through Rstudio but due to the data set being too large for RStudio. Since I couldn't really use it and I had to manipulate it with Excel. I also technical difficulties at home with my laptop so I had to use my iPad and stick with Excel to manipulate my data. 
The first problem I had was that the original data set had 486,230 blank cells, I used the =COUNTBLANK() function in order to count how many blank cells there were and that was the file that had all the U.S. information. Just so you can imagine the total size of this data set had 32,412 rows and 66 columns, I did the math for fun and the blank cells consist of about 22.7% of the data. 
In order to pull out the Washington information I had to highlight all the data set and use the "Sort" function in Excel, which is located under the "Data" tab in "Sort & Filter." Then I got the information to organize itself categorcially based on states. Then I highlighted the Washington Data and copied it and moved it to a spreadsheet by itself. Then I had to clean the blank cells in the Washington Data, which consisted of 9,214 cells. 
I noticed that the Washington Data Set had columns that seemed blank, so I inserted a new row and decided to use the ISBLANK() function, which is a boolean function that returns true if the cell is blank otherwise it returns false, to label which data had the blank columns. Then I highlighted the data and organized it based on the value of that row. It divided my Washington Data into a book with the left having the blank columns and the right having the columns with the data. Then I highlighted that and put it into a new book and worked with the completed data I had.
While I was looking through my new Completed Washington Data I saw that there was some columns that didn't really mention where they were from and I had to figure out why some data had "numerator" and "denominator" in their column title. I noticed that the values were copied from another column and had either "numerator" or "denominator" in their titles. I tried to organize some of the data but when I thought I had if figured out I couldn't get the data to reproduce itself manually by me doing the math, so I decided to leave it alone and use that data if I really needed it. 
Later I noticed that when I looking at the old "empty" data set, the left side of my old Washington Data, I had some data that was all filled out on the bottom part of the excel sheet. I figured out that the reason I didn't see this earlier was when I did the ISBLANK() function I only tested the first row of the column so anything below wouldn't be tested. So when I went through it I saw that the data that was missing was from Febuary 28th, 2020 to July 14th, 2020. I didn't really know why it was missing but decided to work with the data I did have. 
That data was about the patients that were in the hosipital and they were orgainzed based on age groups. 
I didn't really have to clean for blank cells but I did have to figure out what data was duplicated in that New Completed Washington Data. 

Visualization: 

Table and line graph of the deaths per month:
	Deaths
March	13
April	224
May	106
June	93
July	106
August	140
September 	78
October 	110
November	212
December	486
January 	345
February 	237
March	111
April	169
May	176
June	152
July	109
August	421
September	745
October 	448

![Deaths_Line](https://user-images.githubusercontent.com/44421001/144731226-2be1e148-96cf-478c-a00f-a9c5ef040b9d.png)

Table and line graph of the percent of COVID patients in the hosiptal:
Percent of COVID patients	
March	0.0901
April	0.1064
May	0.0711
June	0.0514
July	0.0738
August	0.0584
September 	0.0436
October 	0.0426
November	0.0799
December	0.1223
January 	0.1033
February 	0.0669
March	0.0438
April	0.0705
May	0.0769
June	0.0598
July	0.0558
August	0.1378
September	0.1772
October 	0.1351
![Percent of COVID Patients](https://user-images.githubusercontent.com/44421001/144731575-8e47c654-a21a-4ae7-8936-cd6d602c73f8.png)

Table and Line graph of Critical Staff Shortage:
Critical Staff Shortage	
March	0
April	0
May	0
June	0
July	145
August	416
September 	401
October 	365
November	416
December	451
January 	294
February 	207
March	193
April	266
May	247
June	253
July	302
August	505
September	552
October 	528
![Number of Staff](https://user-images.githubusercontent.com/44421001/144731597-275c826c-c715-4d84-bfcb-790f69b2c68d.png)

Analysis:
I was able to get RStudio to help me analysis the Death information in the dataset. 
![Deaths_Box](https://user-images.githubusercontent.com/44421001/144731913-6adbd453-5369-4ccc-9090-bef57a5ebd7b.PNG)
Tukey five number summary, according to the summary() function in RStudio for the deaths column:
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max.    NA's 
   0.00    3.00    5.00    7.37   10.00   35.00     571 
 Something I learned from the boxplot and Tukey's summary was that we didn't have it too bad as far as deaths due to COVID, here in Washington because at max we had 35 deaths one day and then on average we were having about 8 deaths at most, I rounded up. With our deaths usually being between 3 to 10 people a day. 
 
Another interesting observation I made was that the days the hosiptal had more shortages meant that there was more deaths due to COVID: 
![Deaths_vs_Shortage_scatter](https://user-images.githubusercontent.com/44421001/144732071-4ca0fbaf-5dd4-4bc5-9a01-ae906abf93a3.JPG)
According to RStudio the correlation between those two variable is, 0.554. 



