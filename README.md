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

