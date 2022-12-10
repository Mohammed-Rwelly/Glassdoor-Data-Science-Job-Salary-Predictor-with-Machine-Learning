# Glassdoor-Data-Science-Job-Salary-Predictor-with-Machine-Learning

This project includes detailed steps from exploration data analysis to the whole workflow of building a salary range predictor based on real jobs data scraped from the Glassdoor.

Steps of project :

## 1-Data Collected :

#### 1-1 Create a database :
'datafromglassdoor2'  and table it's name 'GlassdoorDataset2' contain the columns ['City', 'JobId', 'Source', 'CollectedDate', 'JobTitle', 'CompanyName',
       'RatingNumber', 'PostedDate', 'Posted_Date_N', 'Salary', 'jobURL',
       'fullJobDescribtion', 'Size', 'Type_Of_Ownership', 'Sector', 'Founded',
       'Industry', 'Revenue'] .
       
#### 1-2 Scrapping real data :

it's the stongest point of our project this stage around two months.

 what is scarpping data? 
 
 it's amethod for collecting informationn from web pages . 
 
 Why scrapping?
 
Other than the fact that it is fun, Glassdoor’s library provides a limited number of data points. It doesn’t allow you to scrape jobs or reviews. You only get to scrape companies, which was useless in my case
        
Tips about the data scraping step:    
         
a)Some errors may be due to the slow internet speed so adding extra time.sleep functions between page loading steps will help prevent errors
         
b) XPath is helpful to locate the element you want to click on. After you are familiar with the XPath, you may find it actually very
straightforward. First, right-click on the element and select inspect, then right-click on the selected part of HTML code and select
copy XPath.

## 3- Exploratory Data Analysis 

c) after that we store tha data the scrapped to online database which I mean 'datafromglassdoor2' that we had created in the top .

 ## 2- Data Cleaning:
 
 we proceed onto the data cleaning step. Essentially, we will clean and keep the following columns
 
a)Salary Estimate

b)Company Name

c)Job Description

Besides, we will perform some feature engineering steps to generate some new feature columns as the following:

a)Average Salary Estimate

b)City & State

c)Company Age

d)Trending Data Science Tools (‘Python’, ‘R’,‘SQL’, ‘AWS’, ‘Excel’, ‘Spark’, ‘PyTorch’, ‘TensorFlow’,'Mahine Learning' , 'Deep Learning' ,'Hadoop'‘Tableau’, ‘Keras’)

e)To reach to the best performance , we only keep the rows that have the salary estimated from Glassdoor (Glassdoor est.). In other words, for prediction the salary we need to salary in our model So  we drop the row than don't have the salary.
Why Selenuim?
        
There are data points such as company valuation and job location under the “Company” tab and we want to access that
        
information as well. The webpage does not show that content unless the user clicks on the “Company” tab. This makes clicking
       
 on the “Company” tab necessary. Using requests library and doing simple get requests would not work for this type of website.
        
 Therefore, the only way to scrape that data is to write a program that mimics a human user. Selenium is a library that lets
        
 ou code a python script that would act just like a human user.
        
## 3- Exploratory Data Analysis :

1) we will  display the distribuation of the salary for Data Science , Data Engineer and Data Analyst as we can see below

![image](https://user-images.githubusercontent.com/46110270/206856499-dc813f6b-3cda-4e77-8300-46af029cae56.png)




and I got alittle bit more intersting information you can see above the box blots are obviously there are outliers as we can see below


![image](https://user-images.githubusercontent.com/46110270/206856666-df10a56a-4788-4f1f-a1be-d1ecaa149702.png)


, so we must to drop it by finding the IQR for Salary of Data Analyst ,which data points which fall below Q1 – 1.5 IQR or above Q3 + 1.5 IQR are outliers where Q1 and Q3 are the 25th and 75th percentile of the dataset respectively, and IQR represents the inter-quartile range and given by Q3 – Q1 like this :

![image](https://user-images.githubusercontent.com/46110270/206856725-795d658f-7ee5-42c8-9598-4a6fa85b44dd.png)


2) We find the 3 top location underpaid 90K and 3 top location highpaid 90K and The precense of California as the job location in the high paid group , on the other hand ,the precense of GA in the low paid group. the underpaid group locates more at lower salary such as Manhattan as we can see below :


![image](https://user-images.githubusercontent.com/46110270/206856360-fb8d4a87-ee33-4164-9dc8-0cd695625560.png)

3) we find top 10 states hiring data science ,Not suprisingly , a New York-based job is paid more (113K+), but sush a bog gap up to (60K+) a year between New York and other like Massachusetts is still astonishing.Moreover ,regardlessof living cost ,data science professionals

 ![image](https://user-images.githubusercontent.com/46110270/206856911-d91dbaed-4d47-4d60-bc2b-0b4ba365f149.png)



