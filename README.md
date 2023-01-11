# Retail Marketing Project

This repository covers 3 mains types of marketing analysis done on an eCommerce Retail database from [Kaggle](https://www.kaggle.com/datasets/ilkeryildiz/online-retail-listing):
1. Market Basket Analysis
2. Customer Segmentation

## Team Members

| Sl. No.      | Name | UT EID |
| --- | --- | --- |
| 1. | Chyavan Mysore Chandrashekar | CM65624 |
| 2. | Prathyusha Vedulla | PV6269 |
| 3. | Rochan Nehete | rrn479 |
| 4. | Sai Bhargav Tetali | srt2578 |
| 5. | Shubhada Kapre | sk55489 |


## 1. Market Basket Analysis 

Market Basket Analysis is a technique used by retailers to find association between 2 items in their listings. It involves calculating association rule metrics such as lift. More info on the same can be obtained in this [article](https://towardsdatascience.com/a-gentle-introduction-on-market-basket-analysis-association-rules-fa4b986a40ce)

#### Why we do it? 
Using data to determine that products are often purchased together, retailers can optimize product placement, offer special deals and create new product bundles to encourage further sales of these combinations. Hence we can increase sales as well as customer satisfaction using recommendations from MBA. 

Our analysis involves recommending products to users using 2 approaches:
### a. Complementary Products - 
In this we aim to recommend products with Lift > 1 

### b. Substitutive Products - 
This is an extention of the previous approach. Consider 3 products A,B and C. Suppose A and B are found to have a lift > 1 and B and C are also found to have a lift > 1, then there is a high chance that A and C are substitutive products. 

## 2. Customer Segmentation

We aim to segment customers based upon their purchase behavior. To do this we use RFM(Recency, Frequency, Monetary) analysis. We divide customers on the basis of:
Recency: How recently has the customer made a transaction with us
Frequency: How frequent is the customer in ordering/buying some product from us
Monetary: How much does the customer spend on purchasing products from us


#### Why do we do it?

Using RFM analysis we get to know our most profitable customers. By this information we can optimize the customer service and promotional budgets to maximize profits. 

## Results

1. Market Basket Analysis:
   a. Complementary MBA -
        -We have 4920 products, so a lift table is a 4920x4920 matrix!
        -To calculate the lift between every 2 products, our code took over 31 hours of computation using the most optimal lookup possible.
        -Once we have the lift matrix, we found the top-5 products associated with each product.

Following are some recommendations of Complementary MBA:

![Complementary MBA](../data/Complementary MBA.png "Complementary MBA")


   b. Substitutive MBA - 
        -We could sort the 25 products by descending order of their lift (WRT complementary products), and choose the top-5
        -We could take the top-most from each bucket of 5 in the third layer
        -We could divide the 25 products based on their category, and take only the top-5 products that are of the same category as that of Product A

Following are some recommendations of Substitutive MBA:

![Substitutive MBA](../data/Substitutive MBA.png "Substitutive MBA")

This method does not always work properly. Sometimes it may make errors as well such as:

![Substitutive MBA fail](../data/Substitutive MBA fail.png "Substitutive MBA fail")

2. Customer Segmentation:
The 111 segment is the best customer segment with recent purchases, higher monetary value and higher frequency of purchase, whereas 555 are the complete opposite of the same
![RFM](../data/RFM.png "RFM")





