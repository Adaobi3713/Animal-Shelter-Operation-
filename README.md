# About

This project analyzes historical animal shelter data to uncover:

Seasonal intake trends and monthly variations

Outcome types including adoptions, returns, euthanasia, and transfers

Average length of stay by animal type and intake condition

Live release rates and operational efficiency

The dashboard provides actionable insights for shelter management and helps identify pressure points in animal care and placement.

# Features

Visualize intake and outcome trends by month and year

Track average length of stay by animal type and intake condition

Compute live release rates and other key performance metrics

Interactive filters for animal type, outcome, and year

# Technologies

Data Analysis & Scripting: Python (pandas, matplotlib, seaborn) or R (tidyverse, ggplot2)
Visualization: Power BI Desktop
Data Sources: CSV or Excel shelter datasets
Tools: Excel, Jupyter Notebook, RStudio

# Usage

Open the Power BI file dashboard.pbix to explore trends and KPIs.

Use filters for animal type, intake condition, and outcome type.

Optionally, use the Python script to preprocess or extend the dataset:

import pandas as pd

# Load dataset
df = pd.read_csv("shelter_data.csv")

# Basic stats
total_intake = df.shape[0]
live_release_rate = df[df['Outcome'].isin(['Adoption', 'Return to Owner', 'Transfer/Rescue'])].shape[0] / total_intake * 100

print(f"Total Intake: {total_intake}")
print(f"Live Release Rate: {live_release_rate:.2f}%")

# Monthly intake trend
monthly_trend = df.groupby(df['Intake_Date'].str[:7]).size()
print(monthly_trend)
