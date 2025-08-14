**EXCELL PROJECT ON XYZ COMPANY SALES PERFORMANCE**
1. The company seek for an insight into a raw data which was collected so messy, that necessitate a lot of processes to be carried out in order to create the required insight.
   
3. Click on the link to access the project document https://www.canva.com/design/DAGfGT95YTw/4dZRPq9qYgfSagi-gm0qrg/edit?utm_content=DAGfGT95YTw&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton
   
5. You can also find the data set via a google link https://docs.google.com/spreadsheets/d/1D1ChxifntRQwLNzwLtUkRuq9f5mPWHRtQPvulv_yIag/edit?gid=983623938#gid=983623938

**SQL PROJECT ON XYZ SALES PERFORMANCE**
The refined and cleaned (Using Data cleaning sheet) dataset of XYZ Company was also queried on a Structured Query Language (SQL) to answer some questions, below are the questions and their respective query code to get the data:

1. Retrieve all orders from the USA that were delivered
SELECT *
FROM Data_cleaning
WHERE Country = 'USA'
  AND Delivery_Status = 'Delivered';

2.Calculate the total sales revenue for each product category.
SELECT Product_Category,
       SUM(Quantity * Unit_Price) AS Total_Revenue
FROM Data_cleaning
GROUP BY Product_Category;

3.Find the top 5 countries by total quantity of products ordered.
SELECT Country,
       SUM(Quantity) AS Total_Quantity
FROM Data_cleaning
GROUP BY Country
ORDER BY Total_Quantity DESC
LIMIT 5;

4. Get the average rating for each delivery status.
SELECT Delivery_Status,
       AVG(Rating) AS Avg_Rating
FROM Data_cleaning
GROUP BY Delivery_Status;

5. List all orders where the quantity is negative (possible data entry error).
SELECT *
FROM Data_cleaning
WHERE Quantity < 0;

6. Find the highest-priced product in each product category.
SELECT Product_Category,
       Product_Details,
       MAX(Unit_Price) AS Max_Price
FROM Data_cleaning
GROUP BY Product_Category, Product_Details;

7.Count how many customers used each payment method.
SELECT Payment_Methods,
       COUNT(*) AS Number_of_Customers
FROM Data_cleaning
GROUP BY Payment_Methods;

8. Show all orders placed in 2024 sorted by the most expensive unit price.
SELECT *
FROM Data_cleaning
WHERE YEAR(Order_Date) = 2024
ORDER BY Unit_Price DESC;

9. Find all customers who gave a rating of 1 but the delivery status was "Delivered".
SELECT *
FROM Data_cleaning
WHERE Rating = 1
  AND Delivery_Status = 'Delivered';
10. Calculate the percentage of orders returned.
    SELECT 
    (SUM(CASE WHEN Return_Flag = 'Yes' THEN 1 ELSE 0 END) * 100.0 / COUNT(*)) AS Return_Percentage
FROM Data_cleaning;
