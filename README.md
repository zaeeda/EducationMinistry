# Education Ministry Analysis
This project shows the trend of dropout enrollments in 3 states in US which include Michigan, Ohio and Washington between 2019 and 2021.

*	Data was collected from the Excel file downloaded
*	Download the Power BI desktop app if you do not have the application on your local computer. Please use the link to download.
*	Open Power BI desktop and click on Get data to get the excel file with the data. The file has two tables in it 1) The course data 2) The student data
*	Click to transform the data in Power BI Power query. I checked null values in both tables by using the arrow down button by the column headers and selected to remove empty values.
*	The student data is a dataset with 6 columns and 7784 rows 
*	The Course data had 7 columns with 67891 rows
*	I ensured that i had the correct data type for each of the columns in the tables.
*	Then i clicked close and apply option at the top left of the power query page to apply all the changes made to the dataset.
*	After the tables were loaded. I needed to create a relationship between the two tables in Power BI. For this step, i use the Model tab on the left of the page and selected a one-to-many relationship on the Student UID in student data to Course data.


### Here is the list of the analysis done on the data to get the trend of:
### Two slicers were added to the dashboard to enable filtering the dashboard as needed by the user
* Student status: This slicer has two options that could be used to filter the dashboard. The options include “Graduated” and “Dropout”
* State: This slicer has three options of the states in the report that can be used to filter the dashboard. The options include “WA”, “OH”, “MI”.

## Percentage student deactivation
*	I utilized the Pie chart to get the percentage distribution of the deactivation reasons over the student dataset. I created a calculated column using DAX formula. The DAX formula looks through the options in the deactivation reasons column and if value is “Graduated” then insert values in the new column as “graduated” else insert the value as “Dropout”. Here is the DAX formula:
Graduated/Not_Graduated = IF('Student Data (2)'[Deactivation Reason]= "Graduated", "Graduated",IF('Student Data (2)'[Deactivation Reason] <> "Graduated","DropOut"))

So, for the pie Chart, to I selected the new column Graduated/Not_Graduated for the Legend of the pie chart and used the values as frequency of students. I formatted the fonts of the labels, the line colors, background, and other aesthetics for the line visual. From this visual, only 22.23% of the student enrolled in the program graduated for the program while other students dropped out of the program.
## Student Enrollment by State
*	I started my analysis with column chart to check for student's enrollment frequency for each of the states. I selected the stacked column chart under the visualization pane in power BI. I used the student data table for this visual. The x-axis of the chart had the state postal code column, and the y-axis of the chart has the student uid. I selected to show the y axis value as percentage instead absolute values. I formatted the Chart using the Format pane on the right side of Power BI app. The conclusion from that plot shows that Washington (WA) has the highest percentage of student's enrollment and Ohio (OH) has the lowest percentage of student enrollment.
## Dropout/ Graduated by month
* This analysis was created to get the trend of the dropout versus the graduates from the program per month. I selected the deactivation date from the student data as the x-axis, I ensured that the date column was in date hierarchy and only selected the month and year option to reflect on the chart. the y- axis of the chart, I utilized the student UID column on the student dataset. For the legend, i selected the calculated column name “Graduated/Not_Graduated”. I formatted the fonts of the labels, the line colors, background and other aesthetics for the line visual
## Monthly Student enrollment by state
* For this analysis, I utilized the line chart visual. Selected the enrollment date column on the student dataset as the x-axis. I ensured that the date column was in date hierarchy and only selected the month and the year option to reflect on the chart. For the y- axis of the chart, I utilized the student UID column on the student dataset. I use the states as the legend. This will enable the chart to show different trends per state. I formatted the fonts of the labels, the line colors, background and other aesthetics for the line visual.
## Monthly graduated by state
* For this analysis, i also used a line chart visual. For the x- axis of the plot, I used the Deactivation date column of the student data. I ensured that the date column was in date hierarchy and only selected the month and the year option to reflect on the chart. For the y- axis, I used the student Id in the student data table and i selected the state postal code column as the Legend for the report This will enable the chart to show different trends per state. In the filter pane of the report, I added the new calculated column “Graduated/Not_Graduated” to the report. This will enable filtering the report using the student status filter. I formatted the fonts of the labels, the line colors, background and other aesthetics for the line visual.
## Monthly credit -earned by state
* The visual used here was the line chart visual for the trend of the credit_earned by state. The visual was pointed to the student course dataset. X- axis used the completion date column of the dataset. I ensured that the date column was in date hierarchy and only selected the month and the year option to reflect on the chart. For the y- axis, I selected the Credit Earned column. This column has a decimal datatype. after the selection of the column as the y-axis value, I ensured that the aggregation of the y- axis is set to sum. Then, i selected the legend as the state postal code column. I formatted the fonts of the labels, the line colors, background and other aesthetics for the line visual.
 
## Conclusions
*	Overall, 22.23% of the students enrolled in the program graduate and the highest population at 77.77% dropped out of the program.
*	The highest number of students that dropped out from the program was in August 2020 with a frequency of 409 students and the highest number of students who graduated was in June 2020 with a frequency of 257 students.
*	WA has the highest percentage of student's enrollment at 54.08% with the peak in September of 2019. WA also have the highest percentage of student that graduated at 18.16% from 2019 to 2021 with the peak in September 2019.
*	The highest percentage of drop out students were due to lack of academic progress at a percentage of 30.54% with WA having the highest percentage at 15.36%. This can be attributed to WA having the highest number of student enrollments.
*	WA and MI have a similar trend on the monthly credit earned. There was a positive increase trend from January 2019 to March 2019. March 2019 also recorded the peak credit earned for both states. There has been decreasing trend from April 2020 to February 2021.


