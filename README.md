# Youtube-Trending-Video-Analysis
Analyzing this data to get an insight into YouTube trending videos to see what is common between these videos. Those insight might also be used by people who want increase popularity of their videos in YouTube. I start with description about the dataset, answering some statistical and analytical questions. Performing EDA (exploratory data analytics) and some data preprocessing.
#### Chosen from: Kaggle
#### No.of rows: 40950
#### No.of columns: 16
#### Data type of columns: Both numeric and character
#### No.of classes: no class labels
## Question 1: Which is the most trending category? 
To get the most trending category, first we will add a column that contains category names based on the values in category_id column. We will use a category JSON file provided with the dataset which contains information about each category.
We can see that videos with contents based on “entertainment” and “music” are the most trending videos in US.
