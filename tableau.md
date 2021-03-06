1. User Filters.
2. Data Server.
3. Live Connection vs Extract data.
4. Measures and Dimension.
5. Continuous and Descrete.
6. Point vs Polygon map.
7. Groups vs Sets.                
8. Order of Filters in Tableau.
9. Level of Detail Expression LOD.
10. Tableau Products.
11. Aggregate Calculation AGG() and ATTR().
12. Using R with Tableau.
13. tabadmin vs tabcmd.
14. js API.

##### 
* Upgrading Tableau Server
* Installing tableau server in distributed environment.
* Tableau 8 vs Tableau 9

##### Questions:-
1. What will you do to bypass authentication to db on user manchine.
  1. Use Extract
  2. embed credentials in data source while publishing tableau data source.
  3. Embedded password: The credentials you used to connect to the data will be saved with the connection and used by everyone who accesses the data source or workbook you publish.
  4. Server run as account: Tableau Server only. The server’s Run As user account will authenticate all users.
2. How to create doughnut chart in tableau?
3. What is window calculation?
  1. **WINDOW_AVG(expression, [start, end])** :- Returns the average of the expression within the window. The window is defined by means of offsets from the current row. Use FIRST()+n and LAST()-n for offsets from the first or last row in the partition. If the start and end are omitted, the entire partition is used.
  
  For example, the view below shows quarterly sales. A window average within the Date partition returns the average sales across all dates. 
  2. Example :- **WINDOW_AVG(SUM([Profit]), FIRST()+1, 0)** computes the average of SUM(Profit) from the second row to the current row.


#### 1. Funnel Chart:
  a. Single bar chart.
  b. Size and sort will give funnel shape.
  c. Lables for data visibilit.
  d. Mark type to area and change row and column
  e. In case of are we need to create a calculation of negative value.
  f. Then put the negative value to left of the measure. then label.

#### 2. Bump Chart:
  a. Line chart Profit numbers per market.
  b. Bump chart will show rank with various market.
  c. Quick table calculation rank, Compute using market.
  d. Right click and make profit pill to descrete. Mark type to be line.
  e. If we use a date then it shoud be descrete.
  
#### 3. Waterfall Chart:
  a. Running total of measure.
  b. Profit over time, quck table calculation running total.
  c. Mark type to gnat, size with negative of profit (Calculated Field).
  d. Negative profit to size and profit to colour.
  
#### 4. Pareto chart:
  a. Used to see how many dimensions are contributing to how much of measure.
  b. Product and sales, Add all members, Sales to rows and sort descending.
  c. Running percent of total sales, Quck table calculation, Edit it and click specific dim and verify that product id is checked making it addressing field.
  d. Add secondary calculation, Percent of total.
  e. Product id on detail shelf, AGG to countDistinct.
  f. Sales, Running total, Edit table calc, verify specific dim checked and secondary calc is percent of total.
  g. Mark type to line.
  h. To add bar chart add new Sales to row self and make dual axis, and Mark type to Bar.
 
#### 5. Bollinger Bands:
  a. Used in Financial analysis to show stocks are under or over sold.
  b. Moving average is the principle.
  c. Moving average is calculated based on specific period of time.
  d. Look Back Period is the previous 20 weeks, as date is week.
  e. We need 2 calc, Moving average and standard deviation, MA and SD creates upper and lower bound.
  f. MA to row shelf and then dual axis, then upper and lower bound.
 
#### 5. Doughnut Chart:
Step 1: Create a pie chart
 
2. In Tableau Desktop, connect to Superstore sample data.
3. Under Marks, select the Pie mark type.
4. Drag Customer Segment to Color.
5. Drag Sales to Size.
6. Click Label, and then select Show mark labels.
7. Resize the pie chart as desired.

Step 2: Switch to the dual-axis chart
 
1. Drag Number of Records to Rows.
2. Drag Number of Records to Rows again.
3. On Rows, right-click both instances of Number of Records, and then select Measure(Sum) > Minimum.
4. On Rows, right-click the second instance of Number of Records, and then select Dual Axis.

Step 3: Change the second pie chart to a circle
 
1. At the bottom of the Marks card, click MIN(Number of Records) (2).
2. Remove Customer Segment from Color.
3. Remove Sales from Size.
4. Click Color, and then choose the same color as the background. In this example, click white.
5. Click Size, and then drag the slider to the left to make the circle smaller.
6. Drag Sales to Label.
7. Right-click on each of the axes and uncheck Show Header.
