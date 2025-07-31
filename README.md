# NYC 311 Service Requests Analysis

This project analyzes NYC 311 Service Requests data from 2024 to identify patterns and trends in city service requests. I built a data pipeline using Python and Jupyter notebooks to process and explore the dataset.

## Project Overview

My goal was to understand how New Yorkers use the 311 system and what this data can tell us about city services. I focused on cleaning the data, exploring different aspects of the requests, and creating informational visualizations.

## Dataset

The data comes from NYC Open Data and includes all 311 service requests from 2024. The original dataset has records going back to 2010 and through 2025, but I filtered it down to just 2024 data for this analysis.

- Source: [NYC Open Data - 311 Service Requests](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9/about_data)
- Records: Approximately 3.4 million requests from 2024
- Format: CSV file

## Files

```
── README.md
── requirements.txt
── 01_data_ingestion.ipynb      
── 02_eda.ipynb                 
── 311_Service_Requests_from_2010_to_Present_20250730.csv
```

## Main Findings

After analyzing the data, I found several patterns:

**Request Volume**
- The most common complaints are noise issues, illegal parking, and problems with heat/hot water
- About 79% of requests get resolved

**Timing Patterns**
- Winter months see spikes in heating-related complaints
- Weekdays have more requests than weekends, specifically Mondays
- Response times vary a lot - some agencies respond in hours, others take weeks

**Geographic Distribution**
- Brooklyn has the most total requests
- But when you account for population, the Bronx has the highest rate per person
- Different boroughs have different types of common complaints

## What's in Each Notebook

**01_data_ingestion.ipynb**
This notebook handles getting the data ready for analysis. I load the CSV file, clean up any issues with the data (like missing values or weird formatting), and save it as a parquet for analysis.

**02_eda.ipynb** 
I look at things like which types of complaints are most common, how requests vary by time of year, and how different boroughs compare to each other. I also created several charts to visualize the findings.

## How to Run This

1. Make sure you have Python installed
2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```
3. Start Jupyter:
   ```bash
   jupyter notebook
   ```
4. Run the notebooks in order (01 first, then 02)

## Charts and Visualizations

I created several charts to show the patterns in the data:
- Bar charts showing the most common complaint types
- Line charts showing how requests change throughout the year
- Comparisons between different NYC boroughs
- Analysis of how quickly different agencies respond to requests

The goal was to make the data easy to understand visually.

## Technical Notes

**Data Processing**
The dataset was pretty large (3.4 million rows), so I had to be careful about memory usage. I chose to save the cleaned data as a Parquet file because it's more efficient than CSV for this kind of analysis.

**Tools Used**
- pandas for data manipulation
- matplotlib and seaborn for creating charts
- numpy for calculations
- Jupyter notebooks for the interactive analysis
- For burough population data - [Metropolis Moving](https://metropolismoving.com/blog/new-york-city-population-in-2024/)

**Challenges**
The biggest challenge was dealing with missing data - some columns were missing values for a significant portion of the records. I had to decide which columns were worth keeping and how to handle the gaps.

For the per-capita analysis, I looked up current population estimates for each borough to make fair comparisons between areas of different sizes.

## What I Learned

This was my first time working with such a large dataset, and I learned a lot about:
- How to efficiently load and process big CSV files and utilize Parquets to more easily load data
- Different ways to visualize patterns in data
- The importance of cleaning data before analysis

## Ideas for Future Work

If I had more time, I'd like to:
- Add maps to show geographic patterns more clearly
- Look at multiple years to see trends over time
