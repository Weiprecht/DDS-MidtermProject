# DDS-MidtermProject  
This GitHub contains the project background, the source code, and all other files for the mid-term project. It also includes general information  

The purpose of this project is to perform an analysis of beer and brewery data to provide insight to management to drive their decision-making  

# General Information: https://thegrowlerguys.com/understanding-abv-and-ibu/  
# What is the IBU?  
Beer is produced by fermenting starch and then flavored with hops.  Hops are the plants that contribute to the bitterness of a beer, but not all hops will make beer bitter.  The bitterness comes from alpha acids found in the resin glands of the flowers of the hop plants.  The degree of bitterness will depend on three factors:

The type of hops used.  Hops with a higher concentration of alpha acids will generate a stronger bitter taste.  These are usually referred to as “bittering hops.”  Hops with less concentration are called “aroma hops” and will add flavors such as citrus, pine, or mango.
The amount of hops added.  It should be no surprise that the more hops added to the brew, the more bitterness there will be.  
When the hops are added, adding hops early in the brewing process will make the beer more bitter.    When hops are added late in the process, the hops contribute more to the beer’s aroma.
IBU stands for International Bitterness Units. The IBU scale ranges from 5 to 100+, although anything over 100 is difficult to differentiate.  Most craft beers range between 10 to 80.  A beer over 60 is considered bitter.

However, before you rely on the IBU score to pick your beer, it’s essential to understand how ABV should impact your decision.

What is ABV?
ABV stands for alcohol by volume.  It is a standard measurement of the alcohol content of the beverage.  Alcohol content will vary depending on the types of base grains used in its production.  During fermentation, yeasts eat the sugars from the grain and create carbon dioxide and alcohol.  Darker, bolder beers are produced with grains with higher sugar content, such as malts, and may also have additives like honey or chocolate.  More sugar in the production will increase the alcohol content and ABV score.

Some dark beers, such as Great Notion’s “Vanilla Double Stack” Imperial Stout, are produced for a rich, smooth taste and contain an ABV of 11% but have an IBU of 0.  Another Stout, Gigantic’s “Fancy Pants” stout, contains an ABV of 7.2% and an IBU of 55, resulting in slightly less sweetness.

What if a beer has a high IBU and a high ABV?
Here’s the tricky part.  A higher ABV can cancel out much of the bitterness of a high IBU.  When a beer contains malts, the sugar content of the malts will make the beer far less bitter but will increase the alcohol content.  This results in a high IBU and high ABV.  Because of this, it’s important to consider how high the ABV score is in conjunction with the IBU and not rely solely on the IBU.  For example, many people will find the “Fancy Pants” stout above tastes smoother than Ex Novo’s “For Whom the Helles Tolls” lager with an ABV of 4.9% and IBU of 22.

#IBU list: https://www.bjcp.org/beer-styles/downloads-and-resources/
# The codebook
Codebook for Beers and Breweries midterm Project

Datasets Overview

The two Dataset Names used for this project are: 
•	The Beers dataset which contains a list of 2410 US craft beers
•	Breweries dataset which contains 558 US breweries.
		 

 Beer Dataset Variable Information 

1. Variable: Name
   - Description: Name of the Beer
   - Data Type:  Character
   - Missing Values: None

2. Variable: Beer_ID
   - Description: Unique Identifier of the beer
   - Data Type: Numeric
   - Missing Values: None

3. Variable: ABV
   - Description: Alcohol volume of the beer
   - Measurement: Continuous
   - Data Type: Numeric
   - Range: 0.0001 to 0.51
   - Missing Values: Yes (Blanks replaced with median values for each State)

4. Variable: IBU
   - Description: International Bitterness Units of the beer
   - Measurement: Continuous
   - Data Type: Numeric
   - Range: 4 to 138
   - Missing Values: Yes (Blanks replaced with median values for each State)

5. Variable: Brewery_ID
   - Description: Brewery ID associated with the beer
   - Range: 4 to 138
   - Missing Values: None

6. Variable: Style
   - Description: Style of Beer
   - Measurement: Discrete
   - Data Type: Factor
   - Missing Values: Yes (Blanks replaced with style values found online)

7. Variable: Ounces
   - Description: International Bitterness Units of the beer
   - Measurement: Discrete
   - Data Type: Numeric
   - Range: 8.4 to 32
   - Missing Values: None





Brewery Dataset Variable Information
1. Variable: Brew_ID
   - Description: Unique Identifier of the brewery
   - Data Type: Numeric
   - Missing Values: None

2. Variable: Name
   - Description: Name of the brewery
   - Data Type:  Character
   - Missing Values: None

3. Variable: City
   - Description: City where the brewery is located.
   - Data Type:  Character
   - Missing Values: None

3. Variable: State
   - Description: US State where the brewery is located.
   - Data Type:  Character
   - Missing Values: None



** Data Cleaning and Transformation **  
All data processing was done in R with the following packages  


library(tidyverse)  
library(pwr)  
library(emmeans)  
library(GGally)  
library(ggplot2)  
library(ggthemes)  
library(multcomp)  
library(pairwiseCI)  
library(usmap)  
library(maps)  
library(knitr)  
library(kableExtra)  
library(class)  
library(patchwork)  
library(caret)  

- Missing Values: The following missing values were found:
Beer Dataset: IBU (1005 records), ABV (62 records), Style (4 records)
-  Missing values treatment:
We do not know why there are gaps in the data for the IBU and ABV. So, we assumed that the data was missing at random (MAR) and would be treated as such.
Missing data imputation - first by seeking open-source information on the values and secondly by taking the median of each state and replacing the remaining missing values with those median values by State.
- Outliers: No Significant outliers were detected in either dataset
- Data Transformation: All data transformation was done using R.

** Additional Notes **  
Additional Datasets were sourced online and were used to supplement and enhance our analysis. These datasets are optional and not an initial requirement for the analysis:  
US_locations_Data  – Used for our geographical map visualization to enhance the storytelling  
US Cities Data – Sourced online from https://simplemaps.com/data/us-cities and used in the geographical map visualization as well.  
Beer Consumption by State – Used to provide further insights on how much consumption by state



- Codebook created by: Emmanuel Opoku and Adam Ercanbrack _
- Date: October 25, 2023

# Files contained in the Githhub

1. Beers.CSV contains beer data  
2. Breweries.csv contains breweries' data  
3. The codebook for beers and breweries is the codebook with variable information  
4. mid_term_project_code final.Rmd is the R markdown file for the project  
5. mid_term_project_code-final.html is the knitted R markdown file  
6. us_locations_data.csv, uscities.csv, and ConsumptionByState.csv are additional files used in enhancing our analysis
7. The mp4 video is a recording of the presentation.
   
