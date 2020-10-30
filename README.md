### Predict the Discount Codes for a Purchasable Item

A new e-commerce app is going live. To provide offers to different segments of customers they have tied up with different vendors and banking partners. Now they have a lots of data but don’t know how to provide the correct offers to the correct customers. You have to predict the columns Coupon Code and Payment Code.
  
#### Data
Data Files  
Train.csv: 8009 x 19 : contains training data  
Test.csv: 6218 x 17 : contains test data  
Submission format.csv: 6218 x 3 : expected results file containing predictions for test data  

#### Data Description

| Columns | Description |
| :--- | :--- |
| customer_id | unique Customer id |
| seller_id | type of gift (clothes/perfumes/etc.) |
| order_checkout_date | category to which the gift belongs under that gift type |
| delivery_eta | Estimated delivery date |
| shipping_charges | approximate shipping charges to deliver the product based on location |
| product_category_code | The categorical code for the product |
| X_1, X_2 | anonymized columns |
| Product_quality_type | segment of the product based on its quality, for ex: in shoes there maybe, local brand there maybe Nike/Adidas |
| Product_mass | weight of the product |
| Product_length, product_height, product_breadth | dimensions of the product |
| Payment_emi_years(max) | EMI tenure max. available if someone opts for |
| Transaction_type | the type of transaction done for the order |
| Order_status | the status of the order, E = executed successfully, A = Alternate product order later, N = Not Available and cancelled, R = Replacement ordered, H = Address not found and returned |
| Coupon_code | The coupon code that should be recommended to the customer based on the product (Electronics (ELEC), Clothing (CLOTH), etc.) |
| Payment_code | The payment code based on the mode of payment that the customer prefers to use mostly. (Google Play (GPAY), Card Payment (HSBC/HDFC) |
	
#### Evaluation Criteria
The evaluation metric will be the mean of the weighted avg. of the recall score generated for both the y-variables 

score1 = 100 x recall\_score(actual\_values['payment\_code'], predicted\_values['payment\_code'], average ='weighted')  
score2 = 100 x recall\_score(actual\_values['coupon\_code'], predicted\_values['coupon\_code'], average ='weighted')  
score = (score1+score2)/2
