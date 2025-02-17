# Movie Data Analysis Project
### Table of Content
 - [Project Overview](#project-overview)
 - [Data sources](#data-sources)
 - [Tools](#tools)
 - [Data Cleaning and Preparation](#data-cleaning-and-preparation)
 - [Exploratory Data Analysis](#exploratory-data-analysis)
 - [Results and Findings](#results-and-findings)
 - [Challenges in Analysis](#challenges-in-analysis)

### Project Overview
This data analysis project aims to provide insights into the performance and trends of movies from 2012 to 2016.
By analyzing version aspects of the movie data, we seek to identify patterns, make data-driven recommendations, and gain a deeper understanding of the industry dynamics.

### Data sources
Movie Data: The primary dataset used for the analysis is the [Movies Data Analysis Dashboard.xlsx](https://github.com/user-attachments/files/16401524/Movies.Data.Analysis.Dashboard.xlsx)
file, containing detailed information about each movie's names, budget, actors, directors etc.

### Tools
 - Power Query - Used Power Query for Data Cleaning
 - Excel, Pivot Tables - Used for Data Analysis, Reports creation, and visualizations

### Data Cleaning and Preparation
The following tasks have been performed during the initial data preparation phase:
 - Data loading and inspection
 - Handling errors, missing values
 - Data cleaning and formatting

### Exploratory Data Analysis
- Which genres were the most profitable each year?
- Which Director got the best movie?
- Which actors were the most successful?
- What was the best and worst profitable movie?
- What month/year had the best revenue release date?

### Results and Findings
The "Top 5 Movies By Box Office Revenue in USD" section indicates the high-budget movies.
Analyze the relationship between budget size and box office revenue to find the optional budget range that maximizes profitability. 
Avoid overspending unless the data suggests a strong return on investment.

As an example for 2016 year:
 - The best profitable movie was "Lights Out": with a budget Box Office Revenue of over 24 Million dollars
 - The best revenue was the "Batman v Superman" movie with a Box Office Revenue of almost 900 million.
 - The most payable actor was Ben Affleck
 - The most profitable month for new releases was July
![MovieDataDashboard](https://github.com/user-attachments/assets/317c9580-88f0-44eb-a34e-713db12f713e)

### Challenges in Analysis
#### M Language
While working on my file, one of the challenges I encountered was creating a specific M language code for grouping that allowed me to merge genres for future analysis. With two columns for genres, I needed to combine the tables to ensure a consistent format (e.g., Action/Comedy instead of Comedy/Action).

```
= Table.Group(#"Sorted Rows1", {"Movie Title"}, 

                                            {{"Combined Genre", each Text.Combine([Concat Genre], " / "), type text},

                                            {"AllData", each _, 

                                                        type table [Movie Title=nullable text, Release Date=nullable date, Wikipedia URL=nullable text, Concat Genre=nullable text, Director=nullable text, Actor First=nullable text, Actor Second=nullable text, Actor Third=nullable text, Actor Fourth=nullable text, Actor Fifth=nullable text, #"Budget ($)"=nullable number, #"Box Office Revenue ($)"=nullable number]}

                                            }

```
