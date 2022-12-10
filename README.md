# Glassdoor-Data-Science-Job-Salary-Predictor-with-Machine-Learning
This project includes detailed steps from exploration data analysis to the whole workflow of building a salary range predictor based on real jobs data scraped from the Glassdoor.

#Steps of project :

###1- Data Collected :

#### 1-1 Create a database 'datafromglassdoor2'  and table it's name 'GlassdoorDataset2' contain the columns ['City', 'JobId', 'Source', 'CollectedDate', 'JobTitle', 'CompanyName',
       'RatingNumber', 'PostedDate', 'Posted_Date_N', 'Salary', 'jobURL',
       'fullJobDescribtion', 'Size', 'Type_Of_Ownership', 'Sector', 'Founded',
       'Industry', 'Revenue'] .
####1-2 Scrapping real data ,Firstly what is scarpping data ?it's the stongest point of our project this stage around two months because  
        it's amethod for collecting informationn from web pages .
        Why scrapping?
        Other than the fact that it is fun, Glassdoor’s library provides a limited number of data points. It doesn’t allow you to scrape jobs or reviews. You only get to scrape companies, which was useless in my case
        Why Selenuim?
        There are data points such as company valuation and job location under the “Company” tab and we want to access that information as well. The webpage does not show that content unless the user clicks on the “Company” tab. This makes clicking on the “Company” tab necessary. Using requests library and doing simple get requests would not work for this type of website. Therefore, the only way to scrape that data is to write a program that mimics a human user. Selenium is a library that lets you code a python script that would act just like a human user.
        Tips about the data scrapping step:
        Some errors may be due to the slow internet speed so adding extra time.sleep functions between page loading steps will help prevent errors
        XPath is helpful to locate the element you want to click on. After you are familiar with the XPath, you may find it actually very straightforward. First, right-click on the element and select inspect, then right-click on the selected part of HTML code and select copy XPath
