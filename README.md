# Customer-segmentation-with-RFM-and-K-means
# 1. Objective: 
Analyze, evaluate R, F, and M scores and customer segments using traditional RFM and related models. Then draw conclusions about the characteristics of specific customer segments. Calculate the CLTV of each customer and predict the future CLTV value. At the same time, in practical terms, propose some solutions and strategies suitable to each customer segment and improve customer quality.
# 2. PROPOSED RESEARCH MODEL

![image](https://user-images.githubusercontent.com/91537767/220366123-53dabaa7-fb64-4ec0-b959-d7a1a821ef15.png)

- The first stage is to segment customers using the RFM traditional method. Prepare the data, compute the R, F, and M indices, then evaluate it using the obtained dataset. Then, divide customers based on these three scores and conduct customer segment analytics.
- The second stage is to segment customers using the K-means approach. Execute the data transformation and scaling procedure. Clustering the data with K-means and selecting the best k. Finally, analyze customer segments.
- The third stage is to calculate CLTV in the future by BG-NBD and Gamma-Gamma model. Then, segment customers by CLTV prediction and analyze segments.
- The last stage is to summarize the results and conclusions. Then, give recommendations for further research.

# 3. RESULTS AND DISCUSSION
3.1 Customer segment by RFM traditional method

3.1.1 Data understanding

The input dataset is a cross-border internet retail dataset covering all transactions for an online retail shop without a location that was situated in the United Kingdom between December 1, 2010, and December 9, 2011. The firm specializes in selling one-of-a-kind presents for special occasions. Wholesalers make up a large portion of the company's clientele.
The data has about 525461 rows with 28816 orders from 4383 customers from 40 different countries. Before analyzing RFM, the team calculate the total order value, filter out empty customers, delete duplicated rows and select non-negative total order value. After that, choose 3 main columns: customer ID, order date and total order.
3.1.2 RFM analysis
Before conducting the calculation of R, F, and M scoring, the study will briefly analyze the revenue situation of the business, specifically the revenue from returning customers and customers who only buy once.

![image](https://user-images.githubusercontent.com/91537767/220366510-c529fff9-2c08-47b4-a8e3-25986b7e9e4d.png)

This figure demonstrates that revenue from repeat customers is quite high, nearly outperforming revenue from one-time customers. The interesting thing is that at the beginning of April 2010, revenue from one-time customers surpassed that of the repeat consumers. This might be due to marketing activities aimed at attracting new consumers. At the same time, the company's products have a short life cycle, as seen by the high and consistent turnover among returning consumers.
The features of the statistical distribution of RFM scores, such as average, minimum value, maximum value, and quartiles, are given in Table 1 after computing recency, frequency, and monetary for RFM analysis.

![image](https://user-images.githubusercontent.com/91537767/220366675-042185c7-c6cf-40bd-adcf-c0187d21f361.png)

This table reveals that the average customer's latest order was 91 days ago, that a customer will buy around 4.5 orders on average, and that they will spend roughly 2040.5 dollars. The study ranks customers in quintiles according to Zaki et al., 2016. According to previous research, customers whose purchase date is closer (that is, the smaller the R-value) are ranked 5, the R-value is in the highest range, and it is ranked 1. However, with points F and M, there is a contrast. The smaller the F, M values, the rank 1, the F, M in the highest range, the rank 5. Next, we rank R,F, M in 5 levels. Then, we combine RFM points and mapping RFM points, customers with an RFM score of 111 are regarded as Hibernating. Customers with an RFM score of 555, on the other hand, are considered the company's best customers.

3.1.3 RFM segmentation

Based on the RFM score and Nga Vu's (Jul 10, 2021) research, the authors divide customers into 10 segments with the RFM criterion in Table 2. For categorization, rely mostly on R and F scores.

<table>
  <tr>
    <th>Customer Segment</th>
    <th>RFM score</th>
    <th>Activity</th>
    <th>Actionable Tip</th>
  </tr>
  <tr>
    <th>Champions</th>
    <th>r’5[4-5]’</th>
    <th>Bought recently, buy often, and spend the most!</th>
    <th>Reward them. Can be early adopters of new products. Will promote your brand.</th>
  </tr>
  <tr>
    <th>Loyal Customers</th>
    <th>r'[3-4][4-5]'</th>
    <th>Spend good money with us often. Responsive to promotions.</th>
    <th>Upsell higher value products. Ask for reviews. Engage them.</th>
  </tr>
  <tr>
    <th>Potential Loyalists</th>
    <th>r'[4-5][2-3]'</th>
    <th>Recent customers, but spent a good amount and bought more than once.</th>
    <th>Offer membership or loyalty to the program, and recommend other products.</th>
  </tr>
  <tr>
    <th>New Customers</th>
    <th>r'51'</th>
    <th>Bought most recently, but not often.</th>
    <th>Provide onboarding support, give them early success, and start building relationships.</th>
  </tr>
  <tr>
    <th>Promising</th>
    <th>r'41'</th>
    <th>Recent shoppers, but haven’t spent much.</th>
    <th>Create brand awareness, offer free trials</th>
  </tr>
  <tr>
    <th>Need Attention</th>
    <th>r'33'</th>
    <th>Above average recency, frequency, and monetary values. May not have bought it very recently though.</th>
    <th>Make limited-time offers, and Recommend based on past purchases. Reactivate them.</th>
  </tr>
  <tr>
    <th>About To Sleep</th>
    <th>r'3[1-2]'</th>
    <th>Below average recency, frequency, and monetary values. Will lose them if not reactivated.</th>
    <th>Share valuable resources, recommend popular products or renewals at discount, and reconnect with them.</th>
  </tr>
  <tr>
    <th>At Risk</th>
    <th>r'[1-2][3-4]'</th>
    <th>Spent big money and purchased often. But a long time ago. Need to bring them back!</th>
    <th>Send personalized emails to reconnect, offer renewals, and provide helpful resources.</th>
  </tr>
  <tr>
    <th>Can’t Lose </th>
    <th>r'[1-2]5'</th>
    <th>Made biggest purchases, and often. But haven’t returned for a long time.</th>
    <th>Win them back via renewals or newer products, don’t lose them to competition, talk to them.</th>
  </tr>
  <tr>
    <th>Hibernating </th>
    <th>r'[1-2][1-2]'</th>
    <th>Last purchase was a long back, with low spenders and a low number of orders.</th>
    <th>Offer other relevant products and special discounts. Recreate brand value.</th>
  </tr>
</table>

The above table provides a base for investigating customer classification based on RFM scores. Along with it, there are conclusions about each segment's purchasing behavior as well as recommendations for each of those groups.

![image](https://user-images.githubusercontent.com/91537767/220502448-3224f98c-3703-40b0-9b3b-e2d0f46fc21b.png)
![image](https://user-images.githubusercontent.com/91537767/220502465-0713a32c-c55b-4cf9-bb8f-198e2b3bbc9b.png)
![image](https://user-images.githubusercontent.com/91537767/220502498-aebe39d5-03cc-4e63-8304-3a9db108a83a.png)
![image](https://user-images.githubusercontent.com/91537767/220502520-85bda76b-f6ca-48c8-9d42-b05edd11f989.png)
![image](https://user-images.githubusercontent.com/91537767/220502537-bd75b156-e09b-4e0b-a98e-c6b8febe77da.png)

These figures show a visualization of the proportion of customers, average purchase frequency, the average date of last purchase, average revenue, and total revenue by customer segment. 
Hibernating has the highest number of customers, but they are the ones with the most recent purchase date, and the frequency and revenue from this customer file are also low. The frequency of purchases is very low and tends to remain low, specifically, the average Recency is very high, more than 213 days, equivalent to more than 7 months without shopping; The average frequency is very low, about once a year. This can be seen as a customer group that brings many risks as well as challenges to businesses. The value contribution of this group of customers is not high and not outstanding but accounts for nearly ¼ of the number of customers of the whole business.
Meanwhile, champions only account for about 15% of total customers but contribute more than 50% of revenue. On average, this group of customers usually has the most recent purchase date of 1 week; The average frequency of purchases is 12 times (on average once a month). And the customer group may be willing to spend a lot of money on shopping. That’s a need to spend a lot of budgets to optimize this customer segment. 
In addition, segments with a small number of customers as well as a small revenue contribution that need less attention such as New Customers and Promising.

3.2 Customer segment by K-means
3.2.1 Data processing

Before doing clustering with K-means, the author checks for outliers and scales data. 

![image](https://user-images.githubusercontent.com/91537767/220502700-31558607-b9f3-489e-a1b1-e4ee42a4886c.png)

The distribution of three variables R, F, and M through Figure 12 is all right-skewed, so it is necessary to transform it to the normal distribution. Based on the research of Box and Cox(1964), the study will transform them near to normally distributed as possible.
Then, the study continues to carry out scaling data by Standardization to bring the data to a distribution range where the mean value of the observations is 0 and the standard deviation is 1. 

![image](https://user-images.githubusercontent.com/91537767/220502817-2df63344-efc0-4429-b089-ab283a91fae2.png)

3.2.2 Cluster customers by K-means

With standard data, the data is put into the K-means model and proceeded to use the Elbow method mentioned in the Literature Review to select the most optimal cluster.

![image](https://user-images.githubusercontent.com/91537767/220502959-60a931e5-a03e-44d3-bb72-32c93d6f8d88.png)
![image](https://user-images.githubusercontent.com/91537767/220502993-26230487-7703-4255-a0cb-6c5eb7d0c78a.png)

Figure 13 shows the result of clustering with the number of clusters from 1 to 10. The SSE line also shows that the elbow flexion point is around 𝑘 = 2 or 𝑘 = 3. To ensure the k which is best optimized, we use with the KElbowVisualizer library from Python to find this k. The answer is shown in Figure 14, k = 3 is the number of clusters for the study. The last step is to label clusters for each customer. 

3.3.3 Customer Segment Analysis

![image](https://user-images.githubusercontent.com/91537767/220503069-4222e3d2-c8d5-4d6f-95e0-0a7988db9456.png)

The features such as the number of customers, average of recency, frequency, monetary, and the sum of monetary are given in Table 4. To have a better view, the study conducts visualization with the following figures.

![image](https://user-images.githubusercontent.com/91537767/220503127-4646532c-639c-4c8d-bc7d-bcf0a0c80663.png)
![image](https://user-images.githubusercontent.com/91537767/220503153-81708f4d-d726-41e8-8a02-300ce4b92abf.png)

The number of customers in the 3 clusters is quite similar, although the number in cluster 1 is 10% less than that of cluster 2, in general, it is not too big of a difference. However, revenue by cluster 1 is accounted for 74,2%, approximately 3 times the total of cluster 0 and cluster 2.

![image](https://user-images.githubusercontent.com/91537767/220504202-5650997d-2345-4d9e-ba42-f52d75d80d3a.png)

In Figure 17: 
- Cluster 0 has the highest recency, lowest purchase frequency, and purchase value of the 3 clusters.
- Cluster 1 has the smallest recency, the highest buy frequency, and the highest purchase value among the three clusters.
- Cluster 2 has recency, frequency, and monetary at medium levels.
- Cluster 1 can be considered as the champions segment in the RFM model because the last day they buy on average is about 2 weeks, the frequency of purchases is 11 times a year and the amount of spending is also very large. Cluster 0 is a group of consumers that do not contribute much to income since they didn’t purchase about 158 days, only buy once a year, and spend very little money.
Based on the analysis results, the author ranks the clusters according to Gold, Silver and Bronze as cluster 1, 2, 0 respectively and update this label to the dataset.

![image](https://user-images.githubusercontent.com/91537767/220504349-89ad55d6-4ca5-4df7-b6a6-365512180c1b.png)

In Figure 18, the data points in the Gold and Silver clusters are relatively near to each other, but the Bronze cluster contains many scattered points and is quite far from the centroids.

3.3 Calculate CLTV by BG-NBD and Gamma-Gamma model
3.3.1 Calculate CLTV

With the support of Gupta and Lehmann's (2003) research about CLTV, The study computes the CLTV for each customer using the previous RFM calculation findings. CLTV only calculates for customers who have a frequency more than one. 

![image](https://user-images.githubusercontent.com/91537767/220504489-c57809c3-b88e-4cb9-aae5-fa0124b32dc0.png)

Generally, CLTV is also somewhat similar to the traditional RFM model and K-means, when loyal customers, who contribute a lot to the business, always have high CLTV. Champions and Can’t Loose have the highest CLTV in Figure 19. Promising, About to Sleep, New Customers, and Hibernating have the lowest CLTV. 
3.3.2 Predict CLTV in the future

With a theoretical basis and related works on predicting CLTV, from BG-NBD and Gamma-Gamma model, the study conducts CLTV calculation in the next 6 months. In the Pareto/NBD model, the CLTV prediction process needs to use another factor, it is the customer lifetime (T) which is determined as the distance from the customer's initial purchase date to the model implementation date. 

![image](https://user-images.githubusercontent.com/91537767/220504619-0bf3a587-656a-4419-883a-ecf2f29fdf90.png)

The BG-NBD model predicts expected transactions and table 5 is the top 10 customers who will have the most purchases in the next 6 months. The total Expected Number of Transactions (6 Months) calculated is 10443.774543709731. 
The Gamma Gamma model use frequency and monetary to predict customers’ revenue. This model, like the standard CLTV computation, only takes frequencies larger than 1 and orders values greater than 0. Before applying to the model, it is necessary to check the correlation between those two variables to see how much influence the output results. The correlation seems very weak in Figure 20.

![image](https://user-images.githubusercontent.com/91537767/220504661-e5b88fd5-2f63-405e-84ea-9e151fec964c.png)

F and M correlation
![image](https://user-images.githubusercontent.com/91537767/220504715-3aa85c84-fb86-4e60-89da-7a117e1e2558.png)

Top 10 highest revenue customers
The Gamma Gamma model predicts in the next 6 months, the revenue will achieve up to 8594949.15628572$. With the results of 2 models BG-NBD and Gamma-Gamma model, multiply the 2 corresponding values together to calculate the CLTV prediction of each customer. The last result is in Table 7.

![image](https://user-images.githubusercontent.com/91537767/220504813-5425b7ef-caf6-486e-807c-eac3c09362f3.png)
CLTV in the next 6 months
3.3.3 Segment Customer by CLTV and analysis
Customer segmentation by CLTV prediction with 3 levels of A, B, and C corresponding to decreasing CLTV prediction value. Low CLTV is level C and vice versa.

![image](https://user-images.githubusercontent.com/91537767/220504940-9395c472-fb63-4273-bc59-3964b7a5e466.png)
Segment A has the highest average CLTV prediction value and is much higher than the rest. 

![image](https://user-images.githubusercontent.com/91537767/220504968-e2db02c1-fcd1-4d7b-ada7-77083519c589.png)
![image](https://user-images.githubusercontent.com/91537767/220504979-1c86c980-7d9d-44a5-9a1d-6de65dae78ce.png)

With the interval division method, so the number of customers is the same in each segment. However, the revenue is different, the revenue in segment A is similar to K-means, 3 times more than the sum of the other 2 segments.
3.3.4 Conclusion and Recommendation
The study has shown the application of RFM in customer segmentation using many different models such as RFM traditional model, K-means, BG-NBD, and Gamma-Gamma model. 
With the traditional RFM model, combined with business knowledge, especially marketing, it is easy to see the usefulness of the model and gain a deeper understanding of its customers. From there, there are suitable marketing strategies and prioritized budget adjustments for specific customer files. RFM model shows Champions and Loyalists are the top customers.
With K-means, the model will balance 3 factors R, F, and M to segment customers by cluster. K-means shows that it is advisable to focus on Gold cluster customers because of their large revenue.
The K-Means clustering and the predictions of the Pareto/NBD and Gamma-Gamma model were almost matched because of the similarity in the number of customers and the total revenue of each segment is quite similar in the 2 models.




