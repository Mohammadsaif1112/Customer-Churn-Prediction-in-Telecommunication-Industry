# Customer-Churn-Prediction-in-Telecommunication-Industry
 Churn occurs when customers switch from one telecom service provider to another. High churn rates can lead to revenue loss and increased marketing expenses to acquire new customers. Predicting customer churn can help telecom companies take proactive measures to retain customers and improve their service
#Analysis methods
The analysis began with importing the necessary libraries and cleaning the dataset by handling missing values. Exploratory Data Analysis (EDA) was conducted to understand the distribution of variables and identify patterns. I then explored the correlation between variables, particularly with respect to churn. This helped identify factors positively and negatively correlated with
customer churn. Finally, I developed predictive models and compared them. Logistic Regression, Random Forest, Support Vector Machine (SVM), ADA Boost, and XG Boost models were
implemented for customer churn prediction. Evaluation metrics were used to assess the performance of each model.
The analysis was done as detailed below:

The first step is to import necessary libraries for customer churn prediction. 
Below are the required libraries:
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/f145ae20-7813-4238-b92a-a3803318d297)

I will now read the data file in the python notebook

![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/bcc677e1-8452-48e8-8da3-8dd6bafc0b3c)

The output is as shown below: 
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/5b6f57f8-8bc4-4788-a79f-5f69e236895f)

 ![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/8dd5e885-a873-4849-a0df-177965a6e30c)

I will now explore the data to see whether there are any missing values:
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/63defb8a-ef0a-4afa-b807-25d61cb0a0c4)

The output is as shown below:
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/a55c4d02-d2eb-47fc-8344-f3950b222439)

![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/3aaf59b3-99ed-44a4-b1ad-c816d7018d9d)

![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/d0234034-f932-42d0-8974-f6ae2e134848)

Based on the output above, it can be seen that there are 11 missing values for total charges. I am going to remove the 11 missing rows from the dataset.
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/d35a04f3-3ad0-4046-aece-e17c443a7bfe)

The output is as shown below:
 ![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/f9cb5dd7-703e-4731-bbd6-6637df1714d6)

As we can see, all missing values have been handled, and there are no more missing values in the dataset.
 
Since the dataset is already cleaned and organized, I will now find the Correlation of "Churn" with other variables.
 
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/8b137019-e885-4780-98b4-84176a8bcc69)

Month to month contracts, absence of online security and tech support seem to be positively correlated with churn. While, tenure, two year contracts seem to be negatively correlated with churn.
 
Besides, services such as Online security, streaming TV, online backup, and tech support without internet connection seem to be negatively related to churn.
I will explore the patterns for the above correlations below before I delve into modelling and identifying the important variables.
Data Exploration

I will first start with exploring the data set, to better understand the patterns in the data and potentially form some hypothesis. First, I will look at the distribution of individual variables and then slice and dice my data for any interesting trends.
A)	Demographics – helps us understand the gender, age range, partner and dependent status of the customers
1.	Gender Distribution - Approximately half of the customers in the data set are male while the other half are female.
 
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/3dccde98-a7e4-4d24-b3b9-2a3689cdf86b)

![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/977d667e-bdc0-496d-b6ac-42807dbbdaca)
 
2.	% Senior Citizens - Only 16% of the customers who are senior citizens hence most of the customers in the data are younger people.
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/e1dc8b3d-cc2d-408f-983a-b374f93f4963)

3.	Partner and dependent status - Approximately 50% of the customers have a partner, while only 30% of the total customers have dependents.
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/82017a45-1c13-4419-b281-57fd5e75dbec)

I will now look at the % of customers, who have partners, also have dependents.

Among the customers who have a partner, only about half of them also have a dependent, while other half do not have any independents. Besides, 
among the customers who do not have any partner, 80% (majority) of them do not have any dependents.
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/8be03bb9-c0e8-499c-8622-932f0a81154e)

 
B)	Customer Account Information: I will look at the tenure and contract

1.	Tenure: Looking at the histogram below, we can see that a lot of customers have been with the telecom company for just a month, while quite a many have been there for about 72 months. This could be potentially because different customers have different contracts. Therefore, based on the contract they are into it could be more/less easier for the customers to stay/leave the telecom company.
 
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/8b0c0d58-7885-4de6-89f2-0e60bc002082)

2.	Contracts: To understand the graph above, I will first look at the number of customers by different contracts.
As seen in the graph above, most of the customers are in the month-to-month contract. While there are equal number of customers in the 1 year and 2-year contracts.
I will now try to understand the tenure of customers based on their contract type.
 ![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/c44d0883-6722-4110-a886-fa25a1357a80)
 
It is evident that most of the monthly contracts last for 1-2 months, while the 2 year contracts tend to last for about 70 months. This shows that the customers taking a longer contract are more loyal to the company and tend to stay with it for a longer period of time.
This is also what I saw in the earlier chart on correlation with the churn rate.

C)	I will now look at the distribution of various services used by customers

![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/9bd9137f-ed2b-4b4c-a41d-cbe4feed09f8)
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/f2c770dc-86bb-4a6b-b195-be56a4117bcd)
 
D)	The relation between monthly and total charges
As shown in the graph below, the total charges increase as the monthly bill for a customer increases.
 ![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/0a182b39-fc66-48aa-8aec-1f00966b29e4)

E)	I will finally look the predictor variable (Churn) and understand its interaction with other important variables as was found out in the correlation plot.
1.	I will first look at the churn rate in the data
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/35c89852-885d-4db0-a50f-3fd33371d18d)

The data shows that 74% of the customers do not churn. Clearly the data is skewed as we would expect a large majority of the customers to not churn. This is important to keep in mind for my modelling as skewness could lead to a lot of false negatives.
During the modelling section, I will see how to avoid skewness in the data.

2.	I will then explore the churn rate by tenure, seniority, contract type, monthly charges and total charges to see how it varies by these variables.
i.	Churn vs Tenure: As indicated in the plot below, the customers who do not churn, tend to stay for a longer tenure with the telecom company.
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/2cd13d56-e76e-46e8-aac9-eabb333cc418)

ii.	Churn by Contract Type: As seen in the correlation plot, the customers who have a month- to-month contract have a very high churn rate.
 ![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/15a5c615-fce1-4a38-bcd9-e45bf5af3ab5)
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/f5fc042d-0350-422e-aff3-8788bf402144)

iii.	Churn by Seniority: Senior Citizens have almost double the churn rate than younger population.
 ![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/7ebdd5ad-ff9a-4a9a-8a22-a6f36f2cc113)
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/0186e7de-eeb0-4596-a73b-52651910eb37)

iv.	Churn by Monthly Charges: Higher percentage of customers churn when the monthly charges are high.
 ![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/7ddaa475-2a02-45be-834e-5e2033b3e279)
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/b3cb98a3-586f-47b7-b045-ff36837723c7)

v.	Churn by Total Charges: there is a higher churn when the total charges are lower.
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/742fef13-1144-4771-b344-00ca4cc596a2)
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/cd52f11d-03eb-40b3-be80-55dada1fc304)
After doing the Exploratory data analysis (EDA), the next step would be to develop predictive models and compare them.
I will develop Logistic Regression, Random Forest, SVM, ADA Boost and XG Boost

1.	Logistic Regression

I will use the data frame where I had created dummy variables
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/045159fd-5ca3-4bc2-977b-b5c3779d022b)

Create Train & Test Data
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/1dfca1fc-6235-4fa2-b9cf-c988f2d12b03)

Running logistic regression model
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/b84158aa-9969-436c-9420-947086fcc0b7)

To get the weights of all the variables
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/5fadd334-4614-41eb-a04e-d53a0e9fcfb1)

Observations

It is evident that some variables have a negative relation to my predicted variable (Churn), while some have positive relation. Negative relation indicates that likeliness of churn decreases with
that variable. I will summarize some of the interesting features below:

•	As demonstrated in EDA, having a 2-month contract reduces chances of churn. 2-month contract along with tenure have the most negative relation with Churn as predicted by logistic regressions
•	Having DSL internet service also decreases the probability of Churn

•	Total charges, monthly contracts, fibre optic internet services, and seniority can lead to higher churn rates.
2.	Random Forest
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/baed0c79-3c62-45d3-83d8-3c0622d522f2)
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/869161df-e609-46d1-8367-10b981095bdf) 

Observations:

•	From random forest algorithm, monthly contract, tenure and total charges are the most important predictor variables to predict churn.
•	The results from random forest are very similar to that of the logistic regression and in line with what was expected from EDA
3.	Support Vecor Machine (SVM)
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/3f8e190a-9889-4cbb-b2c1-09c91c37a3f8)

Wth SVM I was able to increase the accuracy to upto 82%.
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/f061944c-5075-4939-a38f-7722e43c0d88)

4.	ADA Boost
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/bc8070f4-058c-43f7-9618-ea69fdea2065)

5.	XG Boost
![image](https://github.com/mk2287/Customer-Churn-Prediction-in-Telecommunication-Industry/assets/152664423/a14abe7c-3437-43ae-b602-8138e78824d8)

Conclusion
It is interesting that XG Boost was able to increase the accuracy on test data to almost 83%. This clearly demonstrates that XG Boost performed better compared to all other techniques.
Insights:

•	Correlation Findings: Identified factors positively correlated with churn included month-to- month contracts, absence of online security and tech support. Negative correlations were observed with variables such as tenure and two-year contracts.
•	Machine Learning Models: Logistic Regression highlighted the significance of a 2-month contract and DSL internet service in reducing churn. Random Forest emphasized the
importance of monthly contracts, tenure, and total charges. SVM achieved an accuracy of up to 82%, while XG Boost outperformed other models with an accuracy close to 83%.

