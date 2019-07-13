# indiaMart
IndiaMart Hackathon

A working prototype solution has three part

1. MCAT - Unit wise Min-Max price
2. MCAT - Unit - ISQ - ISQ Option wise --- Min Max price.
3. MCAT Unit wise ---- Three most common prices. (Modes)

***Algorithm/Model used for removing outlier***

**Kmeans for clustering:** For extracting patterns in the price column. We can also consider this step as to identify two different patterns: one being acceptable range of values for Price and the other acting as an outlier.
Standard deviation method for detcting outliers: Removing values that fall ounder 3 Standard deviations on either side.
Code Applied
We have implemented the code in python. Below is the actual code. The program flow is as follows:

Importing necessary packages for developing solutions. Packages like numpy,pandas,sklearn,matplotlib has been used.

## DATA PREPARATION

**Data Access:** The data was provided in an excel sheet with data residing in various sheets. Here we have appended data from all sheets into one source

**Data Cleaning:** The Unit column has redundant and uncleaned values. You can see below that initially number of distinct categories in Unit column was 97. We have cleaned the data using regex to reduce the distinct categories to 31.

**Data Subsetting and clustering :** So the idea is to drill down to category to unit level. For each subset of a given unit and category, we try to create clusters on the Price column. The number of set clusters are two. We select the cluster in which most of the data points falls into. In a sense that the selected cluster predominantly generalizes the data.

**Outlier Detection:** After performing cluster, we select the predominant cluster and perform basic outlier detection to remove data points that fall under extreme ends of data trend. So any value that are above 3 standard deviation on the upper scale and below 3 standard deviation on the lower scale are flaged as outlier and they are removed.

Now the filtered and most suitable data is extracted and we create ranges for each category and unit as output.

## Language/Tech used 
Python Language.

## Any assumptions taken
The actual data will have most intutitive information. For example Price of a product is 5000 and for the same unit is 1000. So the underline assumption is the price is recorded for the same number of quantities. i.e. the number of unit purchased is x and the price is 5000 and for same number of unit x the price is 1000. Per unit price would be more effective.
Seaonality in the data is constant. Say the price for a product is same for all season. Even in the sale perios the price is same.
