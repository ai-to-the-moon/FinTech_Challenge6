# Housing Rental Analysis for San Francisco

This Jupyter notebook explores housing trends in various neighborhoods of San Francisco to find properties that are viable investment opportunities.

This is a challenge assignment from Rice's FinTech Bootcamp program due on July 21, 2022. The purpose of this assignment is to demonstrate our knowledge using the hvplot library and apply it to a real world scenario. 

## Technologies

This program is written in Python (3.7.13) and developed using JupyterLabs notebooks using Windows. We are importing pandas (1.3.5), hvplot (0.7.3), and pathlib libraries (see parenthesis for versions used in program development).

You can install hvplot by using `pip install hvplot`.

## Installation Guide

Downloading the code & associated files using `git clone` from the repository is sufficient to download the program, ensure that the associated libaries (see Technologies section) are installed on your machine as well. If there are any issues with the library functions please refer to the versions used for app development (see Technnologies section for this information as well).  Please note that this is a Jupyter notebook. 

## Usage

This notebook is referencing data stored in the 'Resources' folder (housing_per_year.csv, neighborhoods_coordinates.csv, sfo_neighborhoods_census_data.csv). 

If you are interested in using this notebook to look at another area, the infromation you'll need are the neighborhoods in that area, along with housing unit counts, sales price per square foot statistics, gross rent estimates and neighborhood lat/lon locations. If you don't want to start from scratch, you can just re-populate the csv files with your new information. 

## Code examples

With the hvplot library, it's easy to generate visualizations that you can interact with to look at statistics by area. 

Check out the housing growth with a simple bar chart:
```python
housing_units_by_year.hvplot.bar(x="year",                              y="housing_units",  title="Housing Units in San Francisco from 2010 to 2016")
```
![Bar Chart](Images/zoomed-housing-units-by-year.png)

Look at trends in sales prices and gross rent with a line plot:
```python
prices_square_foot_by_year.hvplot.line(x="year", y="housing_units", title="Sale Price Per Square Foot and Average Gross Rent - 2010-2016 - San Francisco")
```
![Plot](Images/avg-sale-px-sq-foot-gross-rent.png)

Add a drop-down menu to dig deeper to check out the information by neighborhood:
```python
prices_by_year_by_neighborhood.hvplot(title = "Sale Price Per Square Foot and Average Gross Rent - 2010-2016 - By neighborhood",groupby = "neighborhood")
```
![Pricing](Images/pricing-info-by-neighborhood.png)

You can also easily map your data as well:
``` python
all_neighborhoods_df.hvplot.points('Lon','Lat',geo=True,size = "sale_price_sqr_foot", color = "gross_rent", frame_width = 700,frame_height = 500, tiles = 'OSM', title = "Neighborhood Map with Housing Price Information")
```
![Map](Images/6-4-geoviews-plot.png)


## Contributors

Project contributors are the Rice FinTech bootcamp program team (instructor Eric Cadena) who developed the tasks for this project along with myself (Paula K) who's written the code in the workbook.
