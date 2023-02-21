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

