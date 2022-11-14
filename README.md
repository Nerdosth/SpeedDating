# SpeedDating

Project 1 - Group 3:  Analysis of SpeedDating Data





# Question 3: How does an individuals Career Goal influence how they rate themselves vs how they rate their partners attritubes?

First, we need to check how many unique careers are in the data. Then we need to determine which careers we should drop. Including carrers with very few entries would skew the data. Somebody can make the wrong assumption about certain career types with one or two individuals responses compared to a career type with many people.

<img width="684" alt="image" src="https://user-images.githubusercontent.com/76061893/201706111-028ad46d-954c-4665-bc78-9e0b4dfae403.png">

The data we are using has multiple rows per individual and those rows include unique values and duplicate values. Intended Career is duplicate value. To get a proper count I first dropped all duplicates based on Unique ID, keeping only the first entery (keeping the last would work all the same).
<img width="513" alt="image" src="https://user-images.githubusercontent.com/76061893/201706437-3103f4dd-b3a3-411a-b5ea-f553db310682.png">

Now we want to remove any Intended Career with too few participates. I removed Career tpes based on the middle quantile, 50th percentile.

<img width="513" alt="image" src="https://user-images.githubusercontent.com/76061893/201706562-2f8fa813-acb7-42f2-a11f-283eacf7a6a8.png">

Create a new database from the main_df and include only careers listed in the career_count_df. We use the main dataframe because it still includes all the individual datapoints we need to calculate the mean values of attribute ratings later on.

<img width="514" alt="image" src="https://user-images.githubusercontent.com/76061893/201706647-b7c50e29-ed17-4f7e-96a8-d8774635cd9a.png">

Now we want to simplify the dataframe by using the listing the interested columns and using the copy function.
(this is optional but it helps with writing code later on see all the column names in one place)

<img width="517" alt="image" src="https://user-images.githubusercontent.com/76061893/201706753-d17cdc37-7be8-4cbd-8964-1252222035e3.png">

To get the average scores by career type, use the groupby function to combine all the enteries by Intended Career and then calculate the mean of all those values.

<img width="515" alt="image" src="https://user-images.githubusercontent.com/76061893/201706826-210a985a-2520-40a9-8292-e296995bffdf.png">

Merge all these dataframes into one consolidated dataframe. One database will help simplify the coding needed to display the charts later on.

<img width="512" alt="image" src="https://user-images.githubusercontent.com/76061893/201707443-666697af-fb4b-47e2-90de-f2d3682e3d5f.png">

Using Seaborn we are able to use simple coding to create fast scatterplots and export png files. While scatterplots are best used to show many datapoints, We find it also be to a great visual tool to display two variables across many catagories.

<img width="514" alt="image" src="https://user-images.githubusercontent.com/76061893/201707303-e820c608-4ce4-4176-839a-e7c425b1f5cb.png">

