# Uber Trip Analysis Dashboard (Power BI)

## Project Objective
The primary goal of this project is to analyze Uber trip data using Power BI to gain actionable insights into booking trends, revenue generation, and trip efficiency. This dashboard is designed to help stakeholders make data-driven decisions to optimize pricing, improve customer satisfaction, and enhance operational efficiency.

---

## Dashboards & Key Features

This Power BI report is divided into three main pages:

### 1. Dashboard 1: Overview Analysis 
This dashboard provides a high-level summary of key performance indicators and core business metrics.

* **KPI Cards:** Displays primary metrics:
    * Total Bookings 
    * Total Booking Value (Revenue) 
    * Average Booking Value 
    * Total Trip Distance 
    * Average Trip Distance 
    * Average Trip Time
* **Dynamic Measure Selector:** A slicer that allows the user to dynamically change the visuals to analyze **Total Bookings**, **Total Booking Value**, or **Total Trip Distance** . All charts on the page update based on this selection.
* **Core Analyses:**
    * **Performance by Payment Type:** (e.g., Card, Cash, Wallet)
    * **Performance by Trip Type:** (Day vs. Night)
    * **Vehicle Type Analysis:** A matrix visual shows all KPIs broken down by vehicle type, with conditional formatting to highlight high/low performance.
    * **Daily Booking Trends:** A line chart showing total bookings by day to identify peak days and fluctuations.
* **Location Analysis:**
    * Most Frequent Pickup & Drop-off Points 
    * Top 5 Locations by Total Bookings
    * Most Preferred Vehicle by Pickup Location
* **UX Enhancements:**
    * **Slicers:** Interactive filters for Date, City, etc..
    * **"Data Details" Bookmark:** A button that displays a pop-up window explaining key metrics and data sources.
    * **"Clear Filters" Button:** A single-click button to reset all slicers on the page.
    * **"Download Raw Data" Button:** An export button using Power Automate or built-in functionality .

### 2. Dashboard 2: Time Analysis 
This dashboard focuses on identifying temporal patterns in ride demand to optimize driver availability and pricing.

* **Global Dynamic Measure:** A central selector for **Total Bookings**, **Total Booking Value**, or **Total Trip Distance** that controls all visuals on this page.
* **Visualizations:**
    * **Heatmap (Matrix):** Shows the concentration of the selected measure by **Hour of the Day (0-23)** and **Day of the Week (Mon-Sun)** .
    * **Area Chart (10-Min Intervals):** Analyzes ride demand in 10-minute buckets to pinpoint exact peak times.
    * **Line Chart (By Day Name):** Compares booking trends across different days of the week (e.g., weekday vs. weekend).

### 3. Dashboard 3: Details Tab 
This page serves as a granular data table to provide in-depth details and support drill-through analysis.

* **Grid Table:** A detailed table displaying key fields for individual trips.
* **Drill-Through Functionality:** Users can right-click any data point on other dashboards (e.g., a specific hour on the heatmap) and "Drill Through" to this page. The table will automatically be filtered to show only the records related to that selection .
* **"View Full Data" Bookmark:** A toggle button that allows the user to remove the drill-through filters and view the complete, unfiltered dataset .

---

## Technical Implementation & Key Concepts
* **Tool:** Power BI
* **Data Modeling:**
    * Activated an **inactive relationship** (using the `USERELATIONSHIP` DAX function) to analyze drop-off locations, as the model had a default active relationship on pickup location.
* **DAX Measures:**
    * Created all base KPIs (Total Bookings, Avg. Booking Value, etc.).
    * Implemented a **disconnected table** and a `SWITCH` or `SELECTEDVALUE` measure to create the dynamic measure selectors.
* **Report Features:**
    * Extensive use of **Bookmarks** to create pop-up windows and reset filters.
    * **Drill-Through** configuration to connect summary visuals to the detail table.
    * **Conditional Formatting** in the vehicle analysis matrix to improve readability.
---

## 🧑‍💻 Author

**Shashi Ranjan**  
📍 Intern at HFFC  
💼 Exploring roles in Business Analytics & Data Analysis  
📧 www.linkedin.com/in/shashi-ranjan-7b6097282

---
