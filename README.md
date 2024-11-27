### **README:Data-Driven-Car-Analysis-Sales-Buyers-and-Trends🚗📊**

---

#### **📋 Overview of the Dashboard**

Welcome to the **Car Sales Analysis Dashboard**! This interactive Power BI report provides in-depth insights into the car sales data. With easy-to-navigate visuals and calculations, you’ll be able to explore various aspects of car sales, trends, and buyer demographics. Here’s a breakdown of what you’ll find:

---

#### **🔍 Key Features:**

- **📅 Time-Based Analysis**: Understand purchase trends over time with the Date Slicer and Line Chart.
- **🚗 Brand and Department Performance**: Analyze the car counts and brand popularity by different categories.
- **👥 Buyer Insights**: Discover the latest car purchases by buyers and calculate the average salary by country.
- **🔑 Make Year Insights**: Understand price trends based on car make year.
- **👩‍🦱👨‍🦰 Gender-Based Brand Popularity**: Dive into the most popular car brands for each gender.

---

#### **🖼️ Dashboard Screenshots**

Here's a glimpse of the dashboard:

![Dashboard Screenshot](https://github.com/Ashokkumar5003/Ashokkumar5003-Data-Driven-Car-Analysis-Sales-Buyers-and-Trends/blob/main/Screenshots/highest%20Avg%20salary%20.png)


---

#### **📐 Page Descriptions and Visuals:**

1. **📅 Page 1: Date Analysis**
   - **Purpose**: Analyze trends in car purchases over time.
   - **Key Visuals**: Date Slicer (Slider) & Line Chart.
   - **What it shows**: Total cars bought over specific time periods.

2. **🚗 Page 2: Car Count Analysis**
   - **Purpose**: Breakdown of car counts by brand, company, and department.
   - **Key Visuals**: Individual Cards for brand/company/department & a Bar Chart.
   - **What it shows**: The count of cars sold for each category.

3. **🛍️ Page 3: Latest Car Purchase by Buyer**
   - **Purpose**: Discover the latest car purchased by each buyer.
   - **Key Visuals**: Table showing buyer name and purchase date.
   - **What it shows**: The latest purchase made by each buyer.
   - ![Dashboard Screenshot](https://github.com/Ashokkumar5003/Ashokkumar5003-Data-Driven-Car-Analysis-Sales-Buyers-and-Trends/blob/main/Screenshots/Latestcarbaught.png) 

4. **💼 Page 4: Average Salary by Country**
   - **Purpose**: Analyze the average salary for buyers across different countries.
   - **Key Visuals**: Bar Chart.
   - **What it shows**: The average salary by country for car buyers.
   - ![Dashboard Screenshot]()


5. **🛠️ Page 5: Make Year Insights**
   - **Purpose**: Discover trends based on car make years.
   - **Key Visuals**: Card displaying the highest average price year & Bar Chart.
   - **What it shows**: The make year with the highest average price and price trends.

6. **👨‍🦱👩‍🦰 Page 6: Popular Brands by Gender**
   - **Purpose**: Analyze the most popular car brands by gender.
   - **Key Visuals**: Clustered Bar Chart & Table.
   - **What it shows**: The most popular brand for male and female buyers.

---

#### **🧮 Key Calculations:**

1. **Total Car Count**:
   ```DAX
   TotalCars = COUNTROWS(CarTable)
   ```

2. **Latest Car Purchase by Buyer**:
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

#### **📚 How to Use the Dashboard:**

1. **💻 Open the Power BI Report**: Open the file in Power BI to start interacting with the visuals.
2. **🔧 Use the Slicers**: Adjust the Date, Country, or other filters to dynamically update visuals.
3. **📊 Explore Visuals**: Hover over charts and cards to view tooltips and get additional insights.
4. **🔍 Use Drill-Down**: In bar charts, click on the data points to drill down for detailed information.

---

#### **🎨 Design & Customization**

- **🌈 Color Scheme**: Chosen to ensure readability and clarity. Primary colors are blue, orange, and green for differentiation.
- **🏷️ Legends & Labels**: All charts and cards are well-labeled with clear titles and legends to indicate what is being displayed.
- **💬 Data Labels**: Enabled for all charts for quick value recognition.

---

#### **⚙️ Technical Details**

- **Power BI Version**: Ensure you are using Power BI Desktop or Service for the best experience.
- **📈 Data Source**: The data used for this dashboard includes car purchase details, buyer demographics, and product information.

---

#### **🚀 Future Enhancements:**

- **🗂️ Advanced Filtering**: Additional filters such as buyer type, vehicle type, and purchase mode.
- **🔄 Data Refresh**: Scheduled data refreshes for real-time insights.
- **🔍 Detailed Drill-Through**: Enable drill-through functionality for deeper data insights based on specific criteria (e.g., region or department).

---

#### **📬 Contact Information**

For questions or feedback, feel free to reach out to me:
- **👤 Name**: Ashok Kumar S
- **📧 Email**: ashokit1012@gmail.com
- **🔗 LinkedIn**: https://www.linkedin.com/in/ashokit1012/


---

### **📌 Closing Thoughts**

This dashboard empowers data-driven decisions for car sales analysis. By using interactive features and detailed insights, businesses can optimize sales strategies, analyze market trends, and understand customer demographics better.

---

**Key Emoji Legends**:
- 🚗 = Car-related insights
- 📊 = Analytics-related sections
- 👥 = Buyer or demographic insights
- 🎨 = Design-related notes
- 💡 = Tips and acknowledgments

---
