# Vietnamese Basketball Association - Data Collection
This project was done as a personal project. [Updated June 2020: Tableau data visualization available here](https://public.tableau.com/profile/daniel.p2355#!/vizhome/VBA_15929788252590/Main?publish=yes)

#### -- Project Status: Completed December 2019

## Project Intro
![Banner](https://github.com/danieltpham/vba-vietnamese-basketball-association/blob/master/banner.JPG)
[Click here to view project output](https://github.com/danieltpham/vba-vietnamese-basketball-association/blob/master/Data-Analysis.ipynb)

## The Process

### Stage 0 - Data Mining with `BeautifulSoup`
The data source used is https://www.asia-basket.com/Asian-Games/basketball.asp, and the data is scraped from each individual game’s final scoreboard (in XML table format) from 2017 – 2019 (3 seasons). Each XML table is reformatted into a Pandas table, and finally saved as a csv.

### Stage 1 - Data Cleaning in `Pandas`
The website uses 2 different formats for XML table in 2017-2018 and 2019, so there are inconsistencies in data representations. Missing stats data and incorrect XML-to-pandas conversions are also tackled in this stage. The individual game data is also collated into 2 big data sets: the team data and individual player data. Primary keys are also constructed to potentially link these two datasets in the next stage.

### Stage 2 - Record Linkage in `Pandas`
This stage involves scraping some meta datasets for each team in each year so that we have two nice relational datasets to work with. One particular issue is the linkage on Name, since VBA has a mix of international players (whose name is in F-M-L order) and local players (whose name is in L-M-F order). I resolve this issue by created a composite key of team, year, and player number instead.

### Stage 3 - Data Visualisation in `Tableau`
Simple EDA Visualisation via Tableau. Link to Tableau dashboard is provided above.

### Stage 4 - Data Analysis and Modelling in `R`
Unlike in the NBA where international stars compete at the same level as the local players, the VBA international players often outshine the local players. This analysis uses clustering and classification techniques to test the hypothesis that the MVPs of each team are indeed international players, and that their stats are higher than that of the local players.

[Click here to view project output](https://github.com/danieltpham/vba-vietnamese-basketball-association/blob/master/Data-Analysis.ipynb)
