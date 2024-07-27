# Movie Data Analysis Project
Table of Content
 - [Project Overview](#project-overview)
 - [Data sources](#data-sources)
 - [Tools](#data)
 - [Data Cleaning and Preparation](#data-cleaning-and-preparation)
 - [Exploratory Data Analysis](#exploratory-data-analysis)
 - [Results and Findings](#results-and-findings)
 - [Challenges in Analysis](#challenges-in-analysis)

### Project Overview
This data analysis project aims to provide insights into the performance and trends of movies from 2012 to 2016.
By analyzing version aspects of the movie data, we seek to identify patterns, make data-driven recommendations, and gain a deeper understanding of the industry dynamics.

### Data sources
Movie Data: The primary dataset used for the analysis is the "Movies Data Analysis Dashboard.xmls" file, containing detailed information about each movie's names, budget, actors, directors etc.

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
The "Top 5 Movies By Box Office Revenue in USD" section indicates the high-budget movies
Analyze the relationship between budget size and box office revenue to find the optional budget range that maximizes profitability. 
Avoid overspending unless the data suggests a strong return on investment.
As an example:
The best profitable movie was "The Devil Inside" in the horror genre: with a budget Box Office Revenue of over 100 Million dollars
The most payable actor was Tom Cruise
The most profitable season for new releases was the summer

### Challenges in Analysis
#### M Language
One of the challenges that I faced through  the work on my file, was a specific code for Grouping in M language which enabled me to combine genres together for future analysis.
There were 2 columns for genres, but for the proper analysis I've had to combine both tables to have the same format: (Action/Comedy and not Comedy/Action)

```
= Table.Group(#"Sorted Rows1", {"Movie Title"}, 

                                            {{"Combined Genre", each Text.Combine([Concat Genre], " / "), type text},

                                            {"AllData", each _, 

                                                        type table [Movie Title=nullable text, Release Date=nullable date, Wikipedia URL=nullable text, Concat Genre=nullable text, Director=nullable text, Actor First=nullable text, Actor Second=nullable text, Actor Third=nullable text, Actor Fourth=nullable text, Actor Fifth=nullable text, #"Budget ($)"=nullable number, #"Box Office Revenue ($)"=nullable number]}

                                            }

```
