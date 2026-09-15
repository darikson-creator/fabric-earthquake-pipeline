# fabric-earthquake-pipeline
I developed an end-to-end data analytics solution using Microsoft Fabric. The project automatically ingests real-time global earthquake data from an API, processes it using a Medallion architecture (Bronze, Silver, Gold), and presents it on an interactive Power BI dashboard that is updated daily.

1). Data Ingestion (Bronze Layer):

I used Python and PySpark within Microsoft Fabric to connect to the public USGS (U.S. Geological Survey) API and extract raw data in JSON format into a Data Lake (Lakehouse).

2). Processing and Cleaning (Silver & Gold Layers):

I applied the Medallion architecture:

Silver: I cleaned the JSON, structured the data into Delta tables, and converted Unix timestamps into human-readable dates.

Gold: I enriched the information. I used a reverse geocoding library (reverse_geocoder) to derive the country code from latitude/longitude coordinates and classified event severity (Low, Moderate, High).

3). Automation and Business (Data Factory + Power BI):

I created a Data Factory pipeline with dynamic parameters to automate the process to run daily. Then, I connected the Gold layer directly to Power BI (using Direct Lake) to display the report in real-time without duplicating data.

4). Key Technologies

Platform: Microsoft Fabric
Languages: Python, PySpark, SQL
Data Engineering: Medallion Architecture (Bronze, Silver, Gold), Delta Tables, Data Factory Pipelines
Visualization: Power BI (Direct Lake, interactive maps)
