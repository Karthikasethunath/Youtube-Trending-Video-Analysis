# Youtube-Trending-Video-Analysis
Analyzing this data to get an insight into YouTube trending videos to see what is common between these videos. Those insight might also be used by people who want increase popularity of their videos in YouTube. I start with description about the dataset, answering some statistical and analytical questions. Performing EDA (exploratory data analytics) and some data preprocessing.
![img1](https://user-images.githubusercontent.com/71560738/162563600-8049f58b-d9b8-4dab-94cc-6c33472aac96.png)

#### Chosen from: Kaggle
#### No.of rows: 40950
#### No.of columns: 16
#### Data type of columns: Both numeric and character
#### No.of classes: no class labels
## DATA OBJECTS
Dataset Details:
video_id,trending_date,title,category_id,publish_time,tags,views,likes,dislikes,comment_count,thumbnail_links,comments_disabled,rating_disabled,video_error,discription.  

Vedio_id (categorical) -	Id of each trending video is provided. To see how many unique video are there.  
Trending_date (numerical) -	Will give the unique date of trending videos  
Title (categorical) -	To see most common words in title.  
Channel_title (categorical)	- To see which channel has most trending video  
Category_id (numerical) -	Which video category has largest number of trending videos  
Publish_time (numeric) -	To see at what time and which day large number of trending videos were published  
Tags (categorical) -	If more number of tags increase the number of views and popularity of trending videos  
Views (numeric) -	Maximum and minimum views for trending videos. Also to see correlation between views and likes  
Likes (numeric) -	Maximum and minimum likes for trending videos  
Dislikes (numeric) -	Maximum and minimum dislikes for trending videos  
Comment_count (numeric) -	How many comments does most video get  
Thumbnail_link (categorical) -	Links for each trending video  
Comments_disabled (boolean) -	How many trending videos have comments diabled  
Ratings_disabled (boolean) -	How many trending videos have rating disabled  
Video_error (boolean) -	How many trending videos have error or removed  
Description (categorical) -	Details about each video.  

## ATTRIBUTE TYPE
#### Qualitative 
Nominal attribute : title,video_id,category_id,tags,thumbnail_links,discription
Binary attribute : comments_disabled,video_error,rating_disabled
Ordinal attribute :  nil. There is no attribute with possible values that have meaningful order or ranking amoung them.
#### Quantitative 
Numeric attribute : interval:publish_time,trending_date, ratio:views,likes,dislikes,comment_count 
Discrete attribute : views,likes,dislikes,comment_count,comments_disabled,video_error,ratings_disabled
Continuous attribute : publish_time 

![plot(1)](https://user-images.githubusercontent.com/71560738/162565195-2d174dd7-0f3f-417b-9ee4-5680f9059b10.png)

## Statistical Questions
### Question 1: Which is the most trending category? 
![question1](https://user-images.githubusercontent.com/71560738/162563614-0c333e14-2350-416a-b6a0-e42474837841.png)
![question1(1)](https://user-images.githubusercontent.com/71560738/162563907-990dda1d-a0e1-4361-9361-c05a11a27892.png)
To get the most trending category, first we will add a column that contains category names based on the values in category_id column. We will use a category JSON file provided with the dataset which contains information about each category.
We can see that videos with contents based on “entertainment” and “music” are the most trending videos in US.
### Question 2: what are the frequent words used in titles? 
![question2(1)](https://user-images.githubusercontent.com/71560738/162563687-6aa64b70-a37c-42f1-8cb8-708fb9a07b75.png)
![question2](https://user-images.githubusercontent.com/71560738/162563694-98642132-9d8c-41ac-a4f7-a61a38271e13.png)
Videos having these words in the title are mostly trended. Therefor youtubers who wish to have a title that will make their video trending can use these words in their title like “official”, “video” etc.
### Question 3: How many videos have dislikes more than like?
![question3(1)](https://user-images.githubusercontent.com/71560738/162563890-d2e6523c-fa7e-4c1d-8753-1a0c1aca04f1.png)
Out of 40949 videos 119 videos have dislikes more than likes. So there is a chance that your video might get more dislikes that like
### Question 4: What is the minimum views to get trending?
![question4(1)](https://user-images.githubusercontent.com/71560738/162563897-dfc31346-a266-493a-98f5-e7e2bccc2ccd.png)
![question4](https://user-images.githubusercontent.com/71560738/162563901-9be0cd84-46a1-489b-8308-51c2681899dd.png)
During 2017-2018 the minimum views any video gets was 549. Regardless to which category and contents it has, minimum views is more that 500.
Therefor the maximum value is 549
### Question 5: Which are the top 5 videos that trend for maximum days in USA 
![question5](https://user-images.githubusercontent.com/71560738/162563926-4a929499-0c36-4632-87e4-541c3e5af96e.png)
Top 5 videos that trend maximum days in US with their title is shown above.
## Analytical Questions
### Question 1: Which video having highest days in trending and why?
![question6(1)](https://user-images.githubusercontent.com/71560738/162564000-cc2d1621-dc0e-45aa-a5df-1756e9d8685e.png)
Splitting trending dates into month,year and date inorder to count most occurrence of videos in the trending list. There is total 10 videos that stayed for 30 days,29 days and 28 days,
We made our mom cry…her dream came true! Was the video that stayed for most days(30). 
The reason why these videos stayed long in the trending list might be because of the category to which they belong. Most these videos are from category_id 24,10 that is from “entertainment” and “music” category which are the mostly viewed category.
![question6](https://user-images.githubusercontent.com/71560738/162564004-b294ab58-8d33-469c-af51-a80baf3ab4a6.png)
![question6(2)](https://user-images.githubusercontent.com/71560738/162564012-37a99f89-2cf9-420f-ab83-2fed8424a813.png) 
We made our mom cry../her dreams came true! Is the video that stayed longest in trending days. 
### Question 2: are most viewers are happy after watching videos?
![question2(1)](https://user-images.githubusercontent.com/71560738/162564180-6e68225e-0c8d-4913-8148-59f50bc0e40b.png)
![question2](https://user-images.githubusercontent.com/71560738/162564182-0e3ada4b-d6ea-4fc0-bb9e-5b843d40e20f.png)
Taking a sentimental analysis of title which is a contextual mining of text which identifies and extracts subjective information in source material, we can see that most of the viewers in USA from year 2017-2018 are neutral. Thus the viewers are either happy or sad are watching videos in YouTube.  Less than 6000 viewers are sad after watching videos. That means number of sad trending videos are less in USA. Number of happy viewers are more that 10000 and neutral viewers are more than 20000.
### Question 3: Will dislike increase with respect to trending days?
![question8(1)](https://user-images.githubusercontent.com/71560738/162564239-e8d1ca1b-14e7-4439-adb3-9348cd7802a2.png)
![question8](https://user-images.githubusercontent.com/71560738/162564249-58d6cd75-3078-4e8c-9d48-564991060aa8.png)
![question8(2)](https://user-images.githubusercontent.com/71560738/162564260-e011709d-6e61-4f80-b44e-c9c8fe0ab0ef.png)
Splitting trending dates into month,year and date inorder to count most occurrence of videos in the trending list.
From the first visualisation we can see that like increases with respect to trending days . how long it stays in trending days that much more the video gets its likes.
From the second visualisation we can see that dislikes also increase with respect to trending days. Users who wish to upload a video might be having a doubt if their videos will get dislikes. Ofcourse, as days increase dislikes will also increase.
### Question 4: how long does a video take to be trending?
![question9(1)](https://user-images.githubusercontent.com/71560738/162564304-875201fc-3fd3-4495-b334-ed455ef8c00c.png) 

count     40949.000000  
mean        412.683460  
std        3504.324463  
min          10.000000  
25%          82.000000  
50%         138.000000  
75%         218.000000  
max      101175.000000  

![question9(2)](https://user-images.githubusercontent.com/71560738/162564314-c29c96d6-0c7d-4c55-8a65-9fe6cde2a37a.png)
80% of videos become trending in less than 246 hours  
85% of videos become trending in less than 289 hours  
90% of videos become trending in less than 337 hours  
95% of videos become trending in less than 417 hours  
97% of videos become trending in less than 491 hours  
99% of videos become trending in less than 680 hours

Splitting the trending and publish day to day,month, year and time and taking a statistical description of trending_time.
The output shows that 80% videos trend within 246 hours and 99% videos trend within 680 hours.
So in USA, videos of any category published in any day during any time becomes trend within 28 days(680 hours) that is in less than a month.
So users who wish to upload a video and are thinking if it might get trend or not, can believe that their videos are most probabily likely to trend with a month.
### Question 5: Compare "Sports" and "Comedy", how many days that there are more total daily views of videos in "Sports" category than in "Comedy" category?
![question10(1)](https://user-images.githubusercontent.com/71560738/162565106-79e4132d-8538-48d4-808e-272b1a785195.png)
First converting the category_id using a JSON file into youtube categories and then splitting them into a table consisting of “comedy” and “sports” category. In the table the views of sports and comedy videos published on the same days are given. From that dates having more total views in sports than comedy are counted. In total there are 83 days.
In overall 205 days are there where comedy and sports videos are released together.
So in 2 years only 205 days both these are released together and out of them USA viewers wish to watch comedy than sports.
So for a given comedy and sports video, viewers watch comedy video.
![question10](https://user-images.githubusercontent.com/71560738/162565114-7b70d68e-37a6-436c-8be9-db307b77c61c.png)
83 days that there are more total daily views of video in "Sports" category than in "Comedy" category.
## EXPLORATORY DATA ANALYSIS
### BASIC STATISTICAL DISCRIPTION:

1. Head():  To see how the first few rows of the dataset looks like
![eda(1)](https://user-images.githubusercontent.com/71560738/162565271-81726ea6-ab1f-4c6a-9fca-5d51cec1bce9.png)
2. Info():  To get some informations about the dataset
![eda(2)](https://user-images.githubusercontent.com/71560738/162565435-b2df1d16-6681-4e9a-88cb-3b2d535043ec.png)
3. Type() : 
Changing to categorical data.
![eda(3)](https://user-images.githubusercontent.com/71560738/162565972-9eb13ff1-9048-4d7a-840b-bd64ab488d5f.png)
![eda(4)](https://user-images.githubusercontent.com/71560738/162565995-b47342b8-cbfc-41ef-b585-965af283eca6.png)
![eda(5)](https://user-images.githubusercontent.com/71560738/162566070-62c3a12c-1621-4caa-bbaa-26f9b4dce6d9.png)
We can see here there are categorical,numerical and boolean values in this data set.
We can see that in total we have 16 columns and 40949 data. 
4. Describe(): gives summary of statistics pertaining to the DataFrame columns. 
![eda(6)](https://user-images.githubusercontent.com/71560738/162566164-e4518119-116e-45cf-ab27-7b768022d7e0.png)
![eda(7)](https://user-images.githubusercontent.com/71560738/162566172-161c0940-460a-4855-8199-d0b114eccb53.png)
Taking the column views lets see its statistical discription,
![eda(8)](https://user-images.githubusercontent.com/71560738/162566179-eafe0afe-bc12-4eff-bf1b-706975d2061f.png)
![eda(9)](https://user-images.githubusercontent.com/71560738/162566181-38281e1d-af1b-41da-85a2-54a975780387.png)  
## DATA VISUALISATION:
### Histogram:
This is a histogram of views. We note that the vast majority of trending videos have 5 million views or less.
Histogram is a chart of poles. plotting histogram is a graphical method for summarizing the distribution of a given attribute. Here we have takes views and likes attribute. We can see that both these Positively Skewed Distribution. it is a type of distribution where the mean, median and mode of the distribution are positive rather than negative or zero.
![eda(10)](https://user-images.githubusercontent.com/71560738/162566265-9fc8923f-cb4e-496f-9393-20d2f48dd6ae.png)
This is a histogram of likes. We note that the vast majority of trending videos have between 0 and 10,00,000 likes.
![eda(11)](https://user-images.githubusercontent.com/71560738/162566295-63041c9e-ffe9-4dab-8202-c180800254b1.png)
### Scatter plot:
Scatter plot between views and likes to visualize the relationship between these variables.
![eda(12)](https://user-images.githubusercontent.com/71560738/162566657-ad631bac-76b7-4908-affe-436908755fea.png)
A scatter plot is one of the most effective graphical methods for determining if there appears to be a relationship,patterns,or trends between two numeric attributes. This is a useful method for providing a first look at the data to see outliers or to explore the possibility of correlation relationship.
![eda(13)](https://user-images.githubusercontent.com/71560738/162566672-542f5244-48be-4f21-af79-a8ee2dcc3d43.png)

Therefor it is positively correlation.Therefor as like increases views also increases.  There is a strong linear relationship between views and likes. The slope of the line is positive (small values of X correspond to small values of Y; large values of X correspond to large values of Y).
### Box plot:
a box plot or boxplot is a method for graphically depicting groups of numerical data through their quartiles. Box plots may also have lines extending from the boxes (whiskers) indicating variability outside the upper and lower quartiles, hence the terms box-and-whisker plot and box-and-whisker diagram. It is a graph that gives you a good indication of how the values in the data are spread out.
![eda(14)](https://user-images.githubusercontent.com/71560738/162566795-3cce368c-8593-4659-9c2d-031438dfd853.png)
![eda(15)](https://user-images.githubusercontent.com/71560738/162566802-c63a882f-6b4d-4903-8b8d-c36236977179.png)
We can see there are heavy outliers.
### Pie chart:
A pie chart (or a circle chart) is a circular statistical graphic, which is divided into slices to illustrate numerical proportion. In a pie chart, the arc length of each slice (and consequently its central angle and area), is proportional to the quantity it represents. 
We can see that out of videos that appeared on trending list , there is a tiny portion with errors.
![eda(16)](https://user-images.githubusercontent.com/71560738/162566835-bfee4a77-a9a7-4dc7-9e22-38e97e062436.png)

### Barplot:
A bar chart or bar graph is a chart or graph that presents categorical data with rectangular bars with heights or lengths proportional to the values that they represent. The bars can be plotted vertically or horizontally. A vertical bar chart is sometimes called a column chart.
A bar graph shows comparisons among discrete categories. One axis of the chart shows the specific categories being compared, and the other axis represents a measured value. 
This is a barplot of channel title according to thier video count. We can see that ESPN has published almost 200 videos between 2017 and 2018.
![eda(17)4](https://user-images.githubusercontent.com/71560738/162566871-95fd45d2-f5d4-467c-82a0-04099e6cf3ab.png)
This is another barplot of number of videos published per day. Here more trending videos are published on Friday and Thursday.
![eda(18)](https://user-images.githubusercontent.com/71560738/162566914-091c4852-ff0f-498e-8735-1cca927b80de.png)
This barplot tells about the publish hours of trending videos. 3-5 p.m are the peak hours.
![eda(19)](https://user-images.githubusercontent.com/71560738/162566931-f3553fe0-b948-4891-b26d-aaf02e2fddd6.png)
### Word cloud:
A word cloud (tag cloud or wordle or weighted list in visual design) is a novelty visual representation of text data, typically used to depict keyword metadata(tags) on websites, or to visualize free form text. Tags are usually single words, and the importance of each tag is shown with font size or color. 
This format is useful for quickly perceiving the most prominent terms to determine its relative prominence. Bigger term means greater weight.
![eda(20)](https://user-images.githubusercontent.com/71560738/162567155-b33f2466-1354-473a-8a39-84e6c10c4c20.png)
![question2](https://user-images.githubusercontent.com/71560738/162567163-c54dba95-d534-4a96-966e-500b168daba1.png)

Ignoring words like "the" and "of", we can see that "-" and "|" symbols occurred a lot in the 40949 trending video titles. We notice  that words "Video", "Trailer",
"How", and "2018" are common in trending video titles.
### Heat map:
A heat map (or heatmap) is a data visualization technique that shows magnitude of a phenomenon as color in two dimensions. The variation in color may be by hue or intensity, giving obvious visual cues to the reader about how the phenomenon is clustered or varies over space.
![eda(21)](https://user-images.githubusercontent.com/71560738/162567208-56cca271-691d-4c24-bd9b-c5b92b2fd87b.png)
We see for example that views and likes are highly positively correlated with a correlation value of 0.85; we see also a high positive correlation (0.80) between likes and comment count, and between dislikes and comment count (0.70).
There is some positive correlation between views and dislikes, between views and comment count, between likes and dislikes.
The correlation map and correlation table above say that views and likes are highly positively correlated.

## CONCLUSION
Taking the case of “Views” column, there is 549 minimum views and 22,00,00,000+ maximum views. So here I have extreame values, thus to comment on “views”, “likes”, “dislikes” or “comments_count” using histogram will be the best option.
For getting a quick summary of columns like “video error”, ”ratings disabled”, ”comments disabled” which are basically binary type attributes, using pie chart is better. 
In the case of categorical data columns like “channel title”,”category id” which numerous channel names and categories in it. To see which channel has most trending videos or to analyze which is the best category using bar charts is best technique. 
In the “ video title” column, I have used word cloud. It represents the frequency of words within a sentence.   
*The best visualisation techniques for this data set will be barchart*.
## DATA PREPROCESSING
### Data cleaning: 
the real – world datatends to be incomplete, noisy, and inconsistent. Data cleaning(or data clensing) routines attempt to fill in the missing values, smooth out noise while identifying outliers, and corect inconsistencies in the data.
Filling in the missing values can be done by igoring the tuple, by filling in the missing values manually, or using a global constant or using measure of central tendencies.
Here i have taken a small portion of my data to find the missing value and replace it. I have found the missing values and replaced it with zeros to get its mean values and then replaced those zeros with the mean values.
#### Missing values:
![pre(1)](https://user-images.githubusercontent.com/71560738/162567424-086f76ea-851b-42c4-a868-efbd1cdd0825.png)
![pre(2)](https://user-images.githubusercontent.com/71560738/162567435-bd14345e-4d88-4a4d-8224-b2b526262cc9.png)
![pre(3)](https://user-images.githubusercontent.com/71560738/162567445-ad92dd6c-f90c-446d-aea7-d363ddabe530.png)

#### binning: 
it is a method to smooth a sorted data value by consulting its “neighbourhood” that is, the values around it. The sorted values are distributed into a number of “buckets” or bins.
In smoothing by bin means, each value in a bin is replaced by the mean values of the bins
In smoothing by bin medians, each bin values is replaced by the bin median.
In smoothing by bin boundaries, the minimum and maximum values in a given bin are identified as the bin boundaries. Each bin is then replaced by the closest boundary values.

Sorted data: 4, 8, 9, 15, 21, 21, 24, 25, 26, 28, 29, 34
      - Bin 1: 4, 8, 9, 15
      - Bin 2: 21, 21, 24, 25
      - Bin 3: 26, 28, 29, 34

Smoothing by bin means:
      - Bin 1: 9, 9, 9, 9
      - Bin 2: 23, 23, 23, 23
      - Bin 3: 29, 29, 29, 29

Smoothing by bin boundaries:
      - Bin 1: 4, 4, 4, 15
      - Bin 2: 21, 21, 25, 25
      - Bin 3: 26, 26, 26, 34

Smoothing by bin median:
      - Bin 1: 9 9, 9, 9
      - Bin 2: 24, 24, 24, 24
      - Bin 3: 29, 29, 29, 29

#### Regression: 

data smoothing can also be done by regression, a technique that confirms data values to a function. Linear regression involves finding the best line to fit two attributes, so that one attribute can be used to predict the other. 

In linear regression, the data are modeled to fit a straight line. A random variable x (predictor variable) with the equation            
y=wx+b       
Where the variance of y is assumed to be constant. The coefficients w and b are regression coefficients.
![pre(4)](https://user-images.githubusercontent.com/71560738/162567493-772590e2-8b28-4d60-a49d-a817a4814bd3.png)
We can see that there is a positive linear relationship between views and likes — in other words, having more views predicts a higher number of likes!
![pre(5)](https://user-images.githubusercontent.com/71560738/162567502-92cb4585-0f23-4368-a3fb-24958100dd6e.png)
Now that we’ve fit a multiple linear regression model to our data, we can predict views from any combination of likes and dislikes. For example, if we wanted to know how many views we would make if we have 200 likes and 10 dislikes. Using the above model we get that there can be 343650 views.

In logistic regression is basically a supervised classification algorithm. In a classification problem, the target variable(or output), y, can take only discrete values for given set of features(or inputs), X. A logistic regression model predicts a dependent data variable by analyzing the relationship between one or more existing independent variables.
![pre(6)](https://user-images.githubusercontent.com/71560738/162567575-f81fa331-be59-4ed6-a7a7-00e9f7d005ce.png)
Here, we can see the confusion matrix in the form of the array object. The dimension of this matrix is 2*2 because this model is binary classification. we have two classes 0 and 1. Diagonal values represent accurate predictions, while non-diagonal elements are inaccurate predictions. In the output, 10074 and 115are actual predictions, and 3 and 6 are incorrect predictions.
			    Accuracy: 0.9991209220550888  
			    Precision: 0.9810126582278481  
			    Recall: 0.9627329192546584  
          
We have got a classification rate of 99%, considered as good accuracy.
Precision: Precision is about being precise, i.e., how accurate your model is. In other words, you can say, when a model makes a prediction, how often it is correct. 
#### Outlier analysis: 
Outliers may be detected by clustering, where similar values are organized into groups or “clusters”. Values that fall outside the set of clusters may be considered as outliers.
A confusion matrix is a table that is used to evaluate the performance of a classification model. we can also visualize the performance of an algorithm. The fundamental of a confusion matrix is the number of correct and incorrect predictions are summed up class-wise.

Outlier detection (also known as anomaly detection) is the process of finding data objects with behaviors that are very different from expectation. Such objects are called outliers or anomalies. An outlier is a data object that deviates significantly from the rest of the objects, as if it were generated by a different mechanism.
We categorize outlier detection methods according to whether the sample of data for analysis is given with domain expert–provided labels that can be used to build an outlier detection model. Second, we divide methods into groups according to their assumptions regarding normal objects versus outliers.
1. Statistical approach: 
As with statistical methods for clustering, statistical methods for outlier detection make assumptions about data normality. They assume that the normal objects in a data set are generated by a stochastic process (a generative model). Consequently, normal objects occur in regions of high probability for the stochastic model, and objects in the regions of low probability are outliers.
(i) Parametric method:
A parametric method assumes that the normal data objects are generated by a parametric distribution.
simple statistical method for univariate outlier detection using normal distribution is the Grubb’s test (also known as the maximum normed residual test). For each object x in a data set, we define a z-score as:
z = |x − x ̅| s , where x ̅ is the mean, and s is the standard deviation of the input data.

Points that lies to the left and right of the red vertical lines are the outliers.
![eda(22)](https://user-images.githubusercontent.com/71560738/162568135-0d882812-12bf-454b-aff9-74e26a41126a.png)
(ii) Nonparametric method:
A nonparametric method does not assume an a priori statistical model. Instead, a nonparametric method tries to determine the model from the input data. In outlier detection using histogram, to determine whether an object, o, is an outlier, we can check it against the histogram. In the simplest approach, if the object falls in one of the histogram’s bins, the object is regarded as normal. Otherwise, it is considered an outlier.
![pre(7)](https://user-images.githubusercontent.com/71560738/162569814-68fbf742-b0d0-4dfb-8111-77c939dd9c7e.png)
2. Clustering based approach: 
Clustering-based approaches detect outliers by examining the relationship between objects and clusters. Intuitively, an outlier is an object that belongs to a small and remote cluster, or does not belong to any cluster. Clustering-based outlier detection using distance to the closest cluster can be done by using DBSCAN.
![pre(8)](https://user-images.githubusercontent.com/71560738/162569830-e4166260-8e2a-4695-9b4d-44ca4c9f2172.png)
### Data integration: 
The merging of data from multiple data stores is data integration. Careful integration can help us to reduce and avoid redundancies and inconsistencies in the resulting data set. This can help improve the accuracy and speed of subsequent data mining process.
#### One hot encoding: 
For categorical variables where no such ordinal relationship exists, the integer encoding is not enough. In fact, using this encoding and allowing the model to assume a natural ordering between categories may result in poor performance or unexpected results (predictions halfway between categories).
In this case, a one-hot encoding can be applied to the integer representation. This is where the integer encoded variable is removed and a new binary variable is added for each unique integer value.
![eda(23)](https://user-images.githubusercontent.com/71560738/162572873-f5461201-c1c1-4b2f-ba8b-450e1a0ebc2a.png)

#### Chi square test:
For nominal data, a correlation relationship between two attributes can be discovered by a chi-square test. The chi-square value(also known as pearsons x^2 statistics) is computed as
Since category_id has higher the p-value, it says that this variables is independent of the response and cannot be considered for model training.
![eda(24)](https://user-images.githubusercontent.com/71560738/162572892-a377e5dc-d3fc-40cf-8afb-8eed3d1c1b66.png)
![eda(25)](https://user-images.githubusercontent.com/71560738/162572894-adb9e45a-d6ba-4b63-8b78-9d1f1cd942dc.png)
### Data reduction: 
It is a technique that can be applied to obtain a reduced representation of the dataset that is much smaller in volume, yet closely maintain the integrity of the orginal data.
#### Dimentionality reduction: 
is a process of reducing random variable or attributes under consideration. Dimentionality reduction methods are wavelet transforms and principal component analysis.
The discrete wavelet transform is a linear signal processing technique that when applied to a data vector X, transforms to a numerically different vector X’ of wavelet coefficient.
*Principal component analysis* searches for k n-dimentional orthogonal vectors that can be used to represent the data, where k≤n. PCA combines the essence of attribute by creating an alternative,smaller set of varibales.
![eda(26)](https://user-images.githubusercontent.com/71560738/162572965-829e549c-dc15-49d0-917b-de9e1581f7e1.png)
![eda(27)](https://user-images.githubusercontent.com/71560738/162572977-abc9451b-c166-4d73-b799-100b05f070c1.png)
![eda(28)](https://user-images.githubusercontent.com/71560738/162572982-38871d2c-de6d-4c3f-8080-7d5aef1560c6.png)
Taking likes,dislikes and comment_count as 3 variables. This is the cluster formed.
Only 2 clusters are formed finally thus the dimentionality is reduced.
The *Singular-Value Decomposition*, or SVD for short, is a matrix decomposition method for reducing a matrix to its constituent parts in order to make certain subsequent matrix calculations simpler.
Here I have taken the first 10 records of 3 columns – views,likes,dislikes. The 3 × 10 matrix is decomposed to U, s and VT. Finally, the 3×10 matrix defined with more columns than rows is reduced. The SVD is calculated and only the first two features are selected. The elements are recombined to give an accurate reproduction of the original matrix.
![eda(29)](https://user-images.githubusercontent.com/71560738/162573039-db356c8a-96bb-4664-879a-fd0751094be6.png)
#### Numerosity reduction:
this technique replace the orginal data volume by alternative small forms of data representation. These techniques may be parametric or non parametric. For parametric method regression  and log-linear models are exapmle. For non parametric models histograms, clustering  and sampling are examples.
K means algorithm is an iterative algorithm that tries to partition the dataset into k pre-defined distinct non-overlapping subgroups (clusters) where each data point belongs to only one group. It tries to make the intra-cluster data points as similar as possible while also keeping the clusters as different (far) as possible. 
It assigns data points to a cluster such that the sum of the squared distance between the data points and the cluster’s centroid (arithmetic mean of all the data points that belong to that cluster) is at the minimum. The less variation we have within clusters, the more homogeneous (similar) the data points are within the same cluster.
![pre(11)](https://user-images.githubusercontent.com/71560738/162573255-d92dbb34-73eb-46fd-9819-c95951ba160e.png)
From the elbow method we can see k=5.
![pre(12)](https://user-images.githubusercontent.com/71560738/162573265-a4d2ce48-0461-44f2-9e6d-27490cda9cb7.png)
![pre(13)](https://user-images.githubusercontent.com/71560738/162573285-59d97fa6-2bed-4641-ada0-669e69d70f3c.png)  
## Classification
### Naïve bayesian theorem: 
Naive Bayes classifiers are a collection of classification algorithms based on Bayes’ Theorem of posterior probability. It is not a single algorithm but a family of algorithms where all of them share a common principle, i.e. every pair of features being classified is independent of each other.  it assumes class-conditional independence that the effect of an attribute value on a given class is independent of the values of the other attributes.  
![pre(14)](https://user-images.githubusercontent.com/71560738/162574657-d033b7a7-84dc-49c7-9c43-4b88268612e7.png)
![pre(15)](https://user-images.githubusercontent.com/71560738/162574670-e89a378e-c40d-4dbb-bddf-42f7c61c2ef5.png)
![pre(16)](https://user-images.githubusercontent.com/71560738/162574672-917c8b6c-e921-4a21-a56b-c7e394cfb043.png)

## NOTES:
#### Training data : is a collection of labeled information that’s used to build a machine learning model. 
•	consists of annotated text, images, video, or audio. 
•	perform its task at a high level of accuracy.
•	most datasets are used multiple times throughout the training process, as this helps to refine the model’s predictions and improve its success rate.
•	E.g.:- In sentiment analysis, training data is usually composed of sentences, reviews or tweets as the input, with the label indicating whether that piece of text is positive or negative.
•	forming at least 70-80% of the total data that is use to build the model. 
In my dataset, YouTube analysis training data – 70% , data with numerical, Boolean and categorical data.
#### Validation data : is primarily used to determine whether the model can correctly identify new data or if it’s overfitting to the original dataset. It helps to adjust hyperparameters and improve model’s accuracy.
In future this model can be validated with 20% of validation dataset.
#### Testing data : is used after both training and validation. It aims to test the accuracy of the final model against the targets. It also provides further confirmation that the model isn’t overfitting to  training and validation data.
In the dataset 30% id for testing, testing is evaluation using precision, recall and accuracy.
#### How much training data needed? : not so much is needed The reason for this is that the number of data points you’ll need for your project is affected by a wide range of factors. there are some factors that often have a high degree of influence on the size of the dataset such as :-
•	Complexity of model -- for every parameter that the model needs to account for, it will need more training data.
In my dataset when number of parameters increases then data size should also increase. As my data set mostly related to comparison between attributes, large dataset can increase accuracy.
•	Training method -- Many traditional machine learning algorithms use structured learning, which has a fairly low ceiling for additional 
data and more datasets are not needed. In contrast, models that use unsupervised learning can improve without structure and figure
out their own parameters. This method requires a lot  more data.
In my dataset I have used both structural and unsupervised learning. Therefor large number of data will be suitable.
•	Labelling needs -- we can annotate a data point in a variety of ways.  As a result, how you label a data point can create significant              variation in the number of data points we need.
in my dataset, in the description column I have used sentiment 
analysis that label each sentences as positive, negative or neutral.
•	Tolerance for error -- Think of the difference between a model that predicts the weather and one that identifies patients who are at          imminent risk of heart attacks. One of these has a much lower threshold for error than the other. The lower your acceptable level of risk, the more data you’ll need to ensure that risk is mitigated.
Even though the data set is large, the threshold for error is lower.
•	Diversity of input -- A chatbot, for example, has to be able to 
understand a variety of languages written in formal, informal, or 
even grammatically incorrect styles. It has to be able to 
understand all of them in order to provide a high level of customer service. Then we will need more data to help the model function in 
that unpredictable environment.
In my data set, in the ‘title’,’channel_name’,’thumpnail_link’ and 
‘description’ column a variety of languages and styles are used. 
Therefor more data set is needed in order to understand them
#### Common method for calculating data needs :
•	Rule of10 -- This is a common, if controversial, rule of thumb which states that a model requires ten times more data than it has degrees of freedom. 
The aim of this rule is to compensate for some of the variability that all of your parameters bring to the model’s input.
If the number of records in our data is greater than (Number of columns – 1) * 10 then the data would be sufficient enough to conduct study. Here In my dataset there are 16 attributes and 40950 records => (16 – 1) *10 = 150 . The number of records is greater than this threshold. Therefore, we have sufficient amount of data.

•	Learning curves – for more evidence-based decision. by plotting results on a graph after each iteration, you can start to see a relationship between dataset size and your model’s ability. This will help you to identify the point where more data starts to provide diminishing returns. 
#### Quality :high quality dataset has following features :-
•	Uniformity – should check for irregularities 
•	Consistency – ensure classes are distributed
•	Comprehensiveness – check that we have enough data
•	Relevancy – identify relevant parameters
•	Diversity – perform user analysis to uncover hidden biases.
There are no irregularities in my data, it is distributed. Important parameters are ‘views’ and ‘likes’.
#### Data collection : the data that we gather must be suitable for the task at hand.
•	Coverage planning 
•	Check for structured and unstructured data
•	Feature extraction
•	Mitigate bias 
There is no noise in my data set. The redundant attribute was first removed by using python.
#### Data cleansing : A clean dataset will have clear, precise parameters and consistent processes for managing outliers and missing values. In other words, it ensures that your data is accurate, complete, and relevant. Some data cleansing problems are:-
•	Duplication
There is no duplication in my data set.
•	Outliers
There are many outliers in my dataset.
•	Structural errors
No structural errors in my dataset.
•	Missing values
There are no missing values in my dataset.



