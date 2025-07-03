# DataTransformation_SurveyMonkey

About the data: The data is from the famous [surveymokey website](http://surveymonkey.com/). It is a website about XYZ....
The raw data contains various different questions with their responses XYZ..... Each question has multiple repsonses...

Transformation:
We initially trasform the data manually by editing it in excel. We pivot the first two rows to accomodate into long format. Then we make some adjustments such that each question has a particular response in order. Then we restructure the 
edited_data in such a way that every question has a response and every response has the correct answer column assoicated with it.

Then we move ahead to python where the data is further cleaned. Start Date, End Date, Email Address and other columns which have no meaning or are blank are dropped. Then we transform the data from wide format to long format for analysis by using pandas. 
