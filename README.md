### **Data Engineering Project Documentation: Earthquake Event Analysis**

**Overview:**

This project focuses on analyzing worldwide earthquake events using USGS earthquake data. I utilized Microsoft Fabric, Power BI, and Microsoft Data Factory to orchestrate a robust data pipeline for processing, analyzing, and visualizing the earthquake data.

---

### **Step 1: Data Lake Creation**

I set up a Data Lake to store the raw earthquake event data, which I fetched from the USGS Earthquake API. The data was collected over a specific time range, stored in JSON format, and uploaded to the Data Lake for further processing.

---

### **Step 2: Bronze Layer (Raw Data Processing)**

Using **PySpark**, I developed a notebook to retrieve data from the USGS Earthquake API. The data was then saved as JSON in the **bronze layer**, which is the raw format for further refinement in the pipeline. The following steps were executed in this layer:

- API Call to fetch earthquake event data.
- Data transformation and storage as JSON for the next stages.

---

### **Step 3: Silver Layer (Data Transformation)**

In the **silver layer**, I created a notebook that transformed the raw JSON data into a structured format for further analysis.

- **Data extraction:** I extracted the relevant fields from the JSON file into a PySpark DataFrame.
- **Transformation:** The data was cleaned and organized, ensuring consistency.
- **Storage:** The structured data was saved into a **table** for further processing in the next layer.

---

### **Step 4: Gold Layer (Location Enrichment)**

In the **gold layer**, I enriched the earthquake data with location information.

- I used **reverse_geocoding** to convert latitude and longitude coordinates into human-readable location names.
- This data was then saved into a final **table**, ready for use in reporting and visualization.

---

### **Step 5: Data Visualization in Power BI**

Using the semantic model built from the **gold layer table**, I created interactive visualizations in **Power BI**. The visualizations provide insights into earthquake occurrences across various countries and the distribution of earthquake magnitudes over time.

**Key Visualizations:**

1. **Earthquakes by Country:** A pie chart visualizing earthquake distribution across different countries.
2. **Earthquakes by Significance:** A bar chart showing the count of earthquakes by significance.
3. **Magnitude Analysis by Country Code:** A bar chart comparing the maximum and minimum magnitudes for each country.


### **Step 6: Data Pipeline Automation using Microsoft Data Factory**

To automate the ETL process, I used **Microsoft Data Factory** to create a data pipeline.

- The pipeline orchestrates the extraction, transformation, and loading (ETL) process, from the bronze layer to the final gold table.
- I scheduled the pipeline to run daily to ensure the data is updated regularly.

---

This project provides valuable insights into earthquake events and allows for real-time analysis and decision-making.

Dashboard :

https://app.powerbi.com/groups/3e485b9b-e8a5-473f-85e5-c92ac624d85c/reports/56f67657-4cfe-4e29-8626-24bbe5b73c76?pbi_source=desktop
