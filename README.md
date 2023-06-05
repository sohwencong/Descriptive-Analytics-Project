## Table of Contents
1. [Objectives](README.md#objectives)
2. [Steps](README.md#steps)
3. [Process & Analyze](README.md#process--analyze)
4. [Analyze & Share](README.md#analyze--share)
5. [Insights & Recommendations](README.md#insights--recommendations)


## Objectives
* **Role**: A business analyst in an apparel company.
* **Goals**: 
1. To identify a business issue, given a dataset.
2. To document and to perform data exploration and data extract, transform, and load (ETL) to build a dimensional model
3. To create interactive data visualizations (charts, reports and dashboards)
4. To document and to present the business insights and recommendations

## Steps
1. The dataset consisted of 13 files of various formats (MS Excel, CSV and XML).

2. Loaded files into MS PowerBI and performed exploratory data analysis. Dimensional model was built. The dataset was then wrangled, cleaned and added with additional features. 

3. Finally, dashboards were created using MS PowerBI. Insights and recommendations were derived from the visualizations. 

## Data Exploration & Dimensional Model Building
### MS PowerBI
1. The dataset (13 files with 15 tables) were loaded into PowerBI and explored. 

![Dimensional_Model](viz/Dimensional_Model.JPG)

2. Dimensional model was built as shown. 
    
    a. Shipments table was merged into orderdetails with OrderID, LineNo and ProductID as key. This merged table was renamed as orderdetails_fact, as it was identified as the fact table as it contained the measures 
       for analysis to be performed upon, such as “unitprice” and “quantity”.

4. 5 dimensions tables are identified / built. They were orders_dim, customers_dim, Employees_dim, products_dim and shippers_dim.

5. orders table was renamed as orders_dim and linked to orderdetails_fact with OrderID as key. 

6. divisions table was merged into customers table with DivisionID as key. The merged table was renamed as customers_dim and linked to orderdetails_fact with CustomerID as key. 

7. team table was merged into employee_team with TeamID as key. employees_new table (New Employees) was appended to employees table. office table was merged into employees table with OfficeID as key and renamed 
as Employees_dim and linked to orderdetails_fact with EmployeeID as key.

8. categories table was merged into products table with CategoryID as key. supplier_band table was merged into suppliers table with SupplierBandID as key and renamed as suppliers_combined. suppliers_combined was 
then merged into products table with SupplierID as key. The merged table was then renamed as products_dim and linked to orderdetails_fact with ProductID as key.

9. shippers was renamed as shippers_dim and linked to orderdetails_fact with ShipperID as key.

## Analyze & Share
### MS PowerBI
1. Loaded the csv file into PowerBI. It took around 10 minutes for the data to be loaded as the files files was more than 1.1GB.  

2. I checked for data type consistency and existence null values. There were null values present in the dataset. Fortunately, the columns that I was interested in did not contain any null values.  

3. The 2 measures that I was interested were the number of trips and ride duration. Hence, I designed the dashboard and created 8 visualizations based on number of trips analysis and average ride duration analysis. 

   a.	By Usertype

   b.	By Hour (of Day)

   c.	By Days (of Week)

   d.	By Month
   
### Dashboard - Number of Trips Analysis
![NoOfTrips_Dashboard](viz/NoOfTrips_Dashboard.JPG)

### Dashboard - Average Ride Duration Analysis
![AvgRideDuration_Dashboard](viz/AvgRideDuration_Dashboard.JPG)

## Insights & Recommendations
### Insights

#### Visualization - Number of Trips By Usertype
![NoOfTrips_Viz_Usertype](viz/NoOfTrips_Viz_Usertype.JPG)

1. 55.5% of the total trips were made by members and 45.5% by casual riders.

#### Visualization - Number of Trips By Month
![NoOfTrips_Viz_ByMonth](viz/NoOfTrips_Viz_ByMonth.JPG)

2. Highest number of trips were made in the months of Jun, July and Aug. These may be due to the fact that the weather is more favourable for cycling. 

#### Visualization - Number of Trips By Day Of Week
![NoOfTrips_Viz_ByDaysOfWeek](viz/NoOfTrips_Viz_ByDaysOfWeek.JPG)

3. The number of trips by member was relatively constant throughout the days of the week, while it spiked during the weekends for casual riders. The number of trips made on Saturdays by casual riders was almost twice that of weekdays. 

#### Visualization - Number of Trips By Hour
![NoOfTrips_Viz_ByMonth](viz/NoOfTrips_Viz_ByHour.JPG)

4. 1700hrs to 1759hrs was the peak hour for both members and casual riders. 

#### Visualization - Average Ride Duration By Usertype
![AvgRideDuration_Viz_Usertype](viz/AvgRideDuration_Viz_Usertype.JPG)

5. Average ride duration by casual riders was 36.8 minutes (71.4%) in contrast to 14.7 minutes (28.6%) by members. In general, average ride duration by casual riders more than doubled that of members. 

#### Visualization - Average Ride Duration By Month
![AvgRideDuration_Viz_ByMonth](viz/AvgRideDuration_Viz_ByMonth.JPG)

6. The average ride duration for both casual riders and members was relatively constant over the months with the peak in Feb. 

#### Visualization - Average Ride Duration By Day of Week
![AvgRideDuration_Viz_ByDayofWeek](viz/AvgRideDuration_Viz_ByDayofWeek.JPG)

7. Ride duration was the highest during the weekends for both casual riders and members. 

#### Visualization - Average Ride Duration By Hour
![AvgRideDuration_Viz_ByHour](viz/AvgRideDuration_Viz_ByHour.JPG)

8. For casual riders, longest average ride durations occurred from 11pm to 4am, ranging from 43 minutes to 60 minutes. 

### Recommendations
1. From insight 2, we know that the number of trips for casual riders were lower than members during the colder months. We can offer a discounted memebership package during these colder months to entice casual riders.

2. From insight 3 and 7, we can come up with a weekend membership promotion package to target the weekend casual riders. 

3. From insight 5, we can come up with a promotion to convert ride duration and the distance travelled into incentives. 

4. From insight 8, we can come up with a night rider membership package to target the longest ride durations from 11pm to 4am. 
