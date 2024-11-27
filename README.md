### **README:Data-Driven-Car-Analysis-Sales-Buyers-and-Trends**

---

#### **Overview**
This Power BI dashboard provides a comprehensive analysis of car sales data, enabling users to explore key metrics, trends, and insights. It includes interactive visuals, KPIs, and filters to answer specific business questions and provide actionable insights.

---

#### **Dashboard Pages and Features**

1. **Date Analysis**
   - **Purpose**: Analyze trends in car purchases over time.
   - **Key Visuals**:
     - **Date Slicer**: Interactive slider to filter data by purchase date.
     - **Line Chart**: Displays the trend of car purchases across time periods.

2. **Car Count Analysis**
   - **Purpose**: Breakdown of car counts by brand, company, and department.
   - **Key Visuals**:
     - **Cards**: Display individual counts for brands, companies, and departments.
     - **Bar Chart**: Shows comparative car counts across categories.

3. **Latest Car Purchase by Buyer**
   - **Purpose**: Identify the most recent car purchase for each buyer.
   - **Key Visuals**:
     - **Table Visual**: Lists buyers, their latest car purchase date, and related details.

4. **Average Salary by Country**
   - **Purpose**: Analyze average salaries of buyers across countries.
   - **Key Visuals**:
     - **Bar Chart**: Displays average salaries by country.
     - **Country Slicer**: Enables users to filter the data for specific countries.

5. **Make Year Insights**
   - **Purpose**: Discover trends in car prices based on their make year.
   - **Key Visuals**:
     - **Card**: Displays the make year with the highest average price.
     - **Bar Chart**: Shows the average car price for each make year.

6. **Popular Brands by Gender**
   - **Purpose**: Analyze the most popular car brands for each gender.
   - **Key Visuals**:
     - **Clustered Bar Chart**: Displays car counts by brand and gender.
     - **Table Visual**: Lists the most popular brand for each gender.

7. **Additional Visuals**
   - **Pie Chart**: Shows the car count distribution by country.
   - **Line Chart**: Trends in car purchases by department over time.

---

#### **Key Calculations**

1. **Total Car Count**:
   ```DAX
   TotalCars = COUNTROWS(CarTable)
   ```

2. **Latest Car Purchase Date by Buyer**:
   ```DAX
   LatestCarBoughtDate = 
   CALCULATE(
       MAX(CarTable[CarBoughtDate]),
       ALLEXCEPT(CarTable, CarTable[Buyer])
   )
   ```

3. **Average Salary by Country**:
   ```DAX
   AvgSalaryByCountry = 
   AVERAGEX(
       FILTER(
           CarTable, 
           CarTable[Country] = SELECTEDVALUE(CarTable[Country])
       ), 
       CarTable[Salary]
   )
   ```

4. **Make Year with Highest Average Price**:
   ```DAX
   MakeYearWithHighestAvgPrice = 
   MAXX(
       TOPN(
           1, 
           SUMMARIZE(
               CarTable, 
               CarTable[MakeYear], 
               "AvgPrice", AVERAGE(CarTable[Price])
           ), 
           [AvgPrice], 
           DESC
       ), 
       CarTable[MakeYear]
   )
   ```

5. **Most Popular Brand by Gender**:
   ```DAX
   MostPopularBrandByGender = 
   MAXX(
       TOPN(
           1,
           SUMMARIZE(
               CarTable,
               CarTable[Brand],
               "CarCount", COUNTROWS(CarTable)
           ),
           [CarCount],
           DESC
       ),
       CarTable[Brand]
   )
   ```

---

#### **Navigation**
- Each page in the dashboard is designed for specific insights.
- Use slicers (e.g., date, country) and legends to filter data dynamically.
- Click on visuals (e.g., bar charts) for cross-filtering across related visuals.

---

#### **Customizations**
- Colors: Ensured a consistent and visually appealing color scheme for all charts.
- Labels: Added clear titles, legends, and axis labels for better understanding.
- Tooltips: Configured for all visuals to show detailed information on hover.

---

#### **How to Use**
1. Open the Power BI dashboard file.
2. Navigate through the pages using the tabs at the bottom.
3. Interact with slicers and visuals to explore the data.
4. Use tooltips and filters to deep dive into specific metrics.

---

#### **Future Enhancements**
- Incorporate additional metrics like buyer demographics or vehicle type.
- Add drill-through options for more granular data exploration.
- Automate data refresh for up-to-date insights.

---

#### **Contact**
For feedback or queries,
contact : 6374517308
Email : ashokit1012@gmail.com
