# Data-Collection-Challenge

# Mars news article and Mars weather analysis

## Task

## What You're Creating

This new assignment consists of two technical products. You will submit the following deliverables:

Deliverable 1: Scrape titles and preview text from Mars news articles.

Deliverable 2: Scrape and analyze Mars weather data, which exists in a table.

## Part 1: Scrape Titles and Preview Text from Mars News

Open the Jupyter Notebook in the starter code folder named part_1_mars_news.ipynb. You will work in this code as you follow the steps below to scrape the Mars News website.

1. Use automated browsing to visit the Mars news link to an external site. Inspect the page to identify which elements to scrape.

2. Create a Beautiful Soup object and use it to extract text elements from the website.

Extract the titles and preview text of the news articles that you scraped. Store the scraping results in Python data

Store each title-and-preview pair in a Python dictionary and, give each dictionary two keys: title and preview.

Store all the dictionaries in a Python list.

Print the list in your notebook.

## Part 2: Scrape and Analyze Mars Weather Data

Open the Jupyter Notebook in the starter code folder named part_2_mars_weather.ipynb. You will work in this code as you follow the steps below to scrape and analyze Mars weather data.

1. Use automated browsing to visit the Mars Temperature Data Site. Inspect the page to identify which elements to scrape.

2. Create a Beautiful Soup object and use it to scrape the data in the HTML table. Note that this can also be achieved by using the Pandas read_html function. However, use Beautiful Soup here to continue sharpening your web scraping skills.

3. Assemble the scraped data into a Pandas DataFrame. The columns should have the same headings as the table on the website. Here’s an explanation of the column headings:

id: the identification number of a single transmission from the Curiosity rover

terrestrial_date: the date on Earth

sol: the number of elapsed sols (Martian days) since Curiosity landed on Mars

ls: the solar longitude

month: the Martian month

min_temp: the minimum temperature, in Celsius, of a single Martian day (sol)

pressure: The atmospheric pressure at Curiosity's location

4. Examine the data types that are currently associated with each column. If necessary, cast (or convert) the data to the appropriate datetime, int, or float data types.

5. Analyze your dataset by using Pandas functions to answer the following questions:

How many months exist on Mars?

How many Martian (and not Earth) days worth of data exist in the scraped dataset?

What are the coldest and the warmest months on Mars (at the location of Curiosity)? To answer this question:
Find the average minimum daily temperature for all of the months.
Plot the results as a bar chart.

Which months have the lowest and the highest atmospheric pressure on Mars? To answer this question:
Find the average daily atmospheric pressure of all the months.
Plot the results as a bar chart.

About how many terrestrial (Earth) days exist in a Martian year? To answer this question:
Consider how many days elapse on Earth in the time that Mars circles the Sun once.
Visually estimate the result by plotting the daily minimum temperature.

6. Export the DataFrame to a CSV file.

## Description

I started part 1 of the challenge by importing the dependencies for Splinter and BeautifulSoup. I opened automated browser and visited the Mars news website. I created a Beautiful Soup object. I inspected the open browser and using Chrome DevTools, I was able to scape the necessary id ('div') and class ('list_text') to begin scraping the titles and previews of each of the Mars news articles. I extracted all of the text elements from the website. I created an empty list to store the dictonaries for the titles and previews. I looped through all of the text elements, extracted the title and preview information from the elements, stored each title and preview pair in a dictionary and added that dictonary to our previously created empty list. I then printed the list to confirm the structure of the data was correct and confirm all the data was scraped successfully. I finished this part of the challenge by quitting the browser.

I started part 2 of the challenge by importing all the neccessary dependencies for webscraping and plotting our analysis results. I opened the automated browser and visited the website for the Mars Weather data. I created a Beautiful Soup object and inspected the browser to scrape the id and class needed to complete the analysis. To store the data, I began by creating two empty lists; one for the table's column headers and the other for the data in each row. I looped through the table's header row using the 'th' class to find each of the column headers and added those to my empty column header list. I then did the same for the row data. This time inspecting the page to find the row data with the 'tr' and 'data-row' elements. I then looped through the data creating a blank list for the row data, found all the row data using the 'td' element, add that information to my newly created empty list, and finally added that list my original empty row data list. Then using the column header list and the row data list, I created a Pandas DataFrame. I printed the first 5 elements to confirm the dataframe was created successfully. Before beginning the analysis, I prepared the data first by getting the datatypes of each of the columns in the DataFrame. Each of the columns returned as an object. I converted each of the columns to the correct datatype using .astype() in order to complete the analysis correctly. Once datatypes were converted, I checked the datatypes again to confirm each column was changed correctly. I then began the analysis by confirming how many months exist on Mars. Using the DataFrame's month column and grouping by the month columns counts for each month, I was able to determine the total months on Mars to be 12. Using the Dataframe's 'sol' column and the .count() function, I was able to determine that there are 1867 Martian days' worth of data. To determine the average temperature by month, I used the 'min_temp' column grouping by the 'month' column and used the .mean() function. I then plotted these results to a bar chart. I sorted the average temperature by month from highest to lowest using the .sort_values() function. I then printed these results to a bar chart to confirm the coldest month of the year being the third month and the hottest month of the year being the eighth month. To get the average pressure by Martian months, I used the 'pressure' column, grouped by the 'month' column and used the .mean() function. I sorted the averages from highest to lowest in order to get a clear picture of the pressure per Martian Month from lowest to highest. To determine how many terrestrial (earth) days there are in a Martian year, I plotted a chart using the 'terrestrial date' column and the temperature column, to show the distance from peak to peak, in order to confirm there is about 675 days in a Martian year. This was also confirmed through a internet search that a Mars year is equivalent to 687 earth days. I then completed the analysis by saving the DataFrame to a CSV file and quit the automated browser.

## References

https://stackoverflow.com/questions/27018622/pandas-groupby-sort-descending-order - Used to confirm thought process on rearranging outputs in order to align visulizations with provided examples.
