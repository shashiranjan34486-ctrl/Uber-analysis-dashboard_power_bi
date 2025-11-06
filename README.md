# Uber Trip Analysis Dashboard (Power BI)

## Project Objective
The primary goal of this project is to analyze Uber trip data using Power BI to gain actionable insights into booking trends, revenue generation, and trip efficiency. [cite_start]This dashboard is designed to help stakeholders make data-driven decisions to optimize pricing, improve customer satisfaction, and enhance operational efficiency[cite: 3, 15].

---

## Dashboards & Key Features

This Power BI report is divided into three main pages:

### [cite_start]1. Dashboard 1: Overview Analysis [cite: 2]
This dashboard provides a high-level summary of key performance indicators and core business metrics.

* **KPI Cards:** Displays primary metrics:
    * [cite_start]Total Bookings [cite: 5]
    * [cite_start]Total Booking Value (Revenue) [cite: 6]
    * [cite_start]Average Booking Value [cite: 7]
    * [cite_start]Total Trip Distance [cite: 8]
    * [cite_start]Average Trip Distance [cite: 9]
    * [cite_start]Average Trip Time [cite: 10]
* [cite_start]**Dynamic Measure Selector:** A slicer that allows the user to dynamically change the visuals to analyze **Total Bookings**, **Total Booking Value**, or **Total Trip Distance** [cite: 17-21]. All charts on the page update based on this selection.
* **Core Analyses:**
    * [cite_start]**Performance by Payment Type:** (e.g., Card, Cash, Wallet) [cite: 22]
    * [cite_start]**Performance by Trip Type:** (Day vs. Night) [cite: 23]
    * [cite_start]**Vehicle Type Analysis:** A matrix visual shows all KPIs broken down by vehicle type, with conditional formatting to highlight high/low performance[cite: 28, 31, 32].
    * [cite_start]**Daily Booking Trends:** A line chart showing total bookings by day to identify peak days and fluctuations[cite: 34, 35].
* [cite_start]**Location Analysis[cite: 39]:**
    * [cite_start]Most Frequent Pickup & Drop-off Points 
    * [cite_start]Top 5 Locations by Total Bookings [cite: 50]
    * [cite_start]Most Preferred Vehicle by Pickup Location [cite: 53]
* **UX Enhancements:**
    * [cite_start]**Slicers:** Interactive filters for Date, City, etc.[cite: 26].
    * [cite_start]**"Data Details" Bookmark:** A button that displays a pop-up window explaining key metrics and data sources [cite: 57-61].
    * [cite_start]**"Clear Filters" Button:** A single-click button to reset all slicers on the page[cite: 62, 63].
    * [cite_start]**"Download Raw Data" Button:** An export button using Power Automate or built-in functionality [cite: 65-67].

### [cite_start]2. Dashboard 2: Time Analysis [cite: 69]
This dashboard focuses on identifying temporal patterns in ride demand to optimize driver availability and pricing.

* [cite_start]**Global Dynamic Measure:** A central selector for **Total Bookings**, **Total Booking Value**, or **Total Trip Distance** that controls all visuals on this page[cite: 73].
* **Visualizations:**
    * [cite_start]**Heatmap (Matrix):** Shows the concentration of the selected measure by **Hour of the Day (0-23)** and **Day of the Week (Mon-Sun)** [cite: 81-84].
    * [cite_start]**Area Chart (10-Min Intervals):** Analyzes ride demand in 10-minute buckets to pinpoint exact peak times[cite: 75, 76].
    * [cite_start]**Line Chart (By Day Name):** Compares booking trends across different days of the week (e.g., weekday vs. weekend)[cite: 78, 80].

### [cite_start]3. Dashboard 3: Details Tab [cite: 86]
This page serves as a granular data table to provide in-depth details and support drill-through analysis.

* [cite_start]**Grid Table:** A detailed table displaying key fields for individual trips[cite: 90, 91].
* **Drill-Through Functionality:** Users can right-click any data point on other dashboards (e.g., a specific hour on the heatmap) and "Drill Through" to this page. [cite_start]The table will automatically be filtered to show only the records related to that selection [cite: 92-94].
* [cite_start]**"View Full Data" Bookmark:** A toggle button that allows the user to remove the drill-through filters and view the complete, unfiltered dataset [cite: 95-97].

---

## Technical Implementation & Key Concepts
* **Tool:** Power BI
* **Data Modeling:**
    * [cite_start]Activated an **inactive relationship** (using the `USERELATIONSHIP` DAX function) to analyze drop-off locations, as the model had a default active relationship on pickup location.
* **DAX Measures:**
    * Created all base KPIs (Total Bookings, Avg. Booking Value, etc.).
    * [cite_start]Implemented a **disconnected table** and a `SWITCH` or `SELECTEDVALUE` measure to create the dynamic measure selectors[cite: 17].
* **Report Features:**
    * [cite_start]Extensive use of **Bookmarks** to create pop-up windows and reset filters[cite: 57, 62, 95].
    * [cite_start]**Drill-Through** configuration to connect summary visuals to the detail table[cite: 92].
    * [cite_start]**Conditional Formatting** in the vehicle analysis matrix to improve readability[cite: 32].
