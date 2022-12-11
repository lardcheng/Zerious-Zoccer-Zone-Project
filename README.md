# Zerious Zoccer Zone Project

This was the final project in the SQL course I took a while ago. I worked together with a team to build a database, tables, and sample data. 

## Introduction

**SITUATION**

This project revolves around a soccer equipment store, named Zerious Zoccer Zone. The store's business is rapidly growing, and they have hired our consulting team to create a centralized database in order to meet the increasing demands. They have certain requirements regarding order placing, inventory tracking, and customer information records. 

**BRIEF**

A centralized database, as stated earlier, is needed to keep all infomration organized. The business needs ways to keep track of individual customers as well as clubs. They need to keep information such as addresses, balances, and sales reps. The storeowner also needs a simple way of tracking inventory. Inventory details include descriptions, colors, sizes, categories, and the number of units and unit price. Lastly, we will need a way to track orders. For every order, we would need to track details such as the customer, date, items purchased, total price, etc. 

**OBJECTIVE**

We will first have to create an entity relationship diagram in order to map out important relationships. Once this has been done, we can begin to creat tables containing the necessary information. We will have to ensure these tables are accurate and can be queried. Afterwards, we will provide recommendations we feel could further improve functionality and efficiency. 

## Business Requirements

Zerious Zoccer Zones has certain requirements that need to be met. They have listed these out for us, and are provided briefly below: 

- Individuals can purchase any items from the inventory
  - Clubs get a discount depending on the number of teams
  - One person in each club places orders for all the uniforms for that team
- Each club has a sales representative
  - The store keeps track of customer information along with their respective sales rep
  - Sales reps work on commission
- The store records information when a customer places an order
- Information about items in inventory are always tracked
  - Al items have a description and price available and belong in a class
 
## Entity Relationship Diagram

After reviewing the business requirements, we had to create an ERD in order to see what how everything related. In the end, we came up with the following connections:

<img width="1000" img height="500" alt="image" src="https://user-images.githubusercontent.com/120063554/206929052-e0fa24bc-608a-4ce4-ae83-e8e3a3603f8f.png">

## Table Setup

Once we had identified all the relationships and tables we needed, we had to create the tables and populate them with sample data. These tables were created in Oracle SQL Developer. 

For example, one table we created was for the clubs, named Z_CLUB. The code for creation is below:

```sql
CREATE TABLE Z_CLUB (
ID NUMBER (10,0),
CLUB_NAME VARCHAR2(50),
TEAM_NUMBER NUMBER(20,0),
MEMBER_NUMBER NUMBER(20,0),
REP_ID NUMBER(10,0),
PRIMARY KEY(ID)
)
```
Screenshots of the tables are provided below:

<img width="1000" img height="500" alt="image" src="https://user-images.githubusercontent.com/120063554/206932225-b49d3385-af2c-4505-9903-63d9ac40b98a.png">

<img width="1000" img height="500" alt="image" src="https://user-images.githubusercontent.com/120063554/206932229-a01b7834-797f-47dd-abd8-24c3dfc9d76a.png">

<img width="1000" img height="500" alt="image" src="https://user-images.githubusercontent.com/120063554/206932232-53a32a72-e024-4b9f-ad49-a96494f1d2a8.png">

<img width="1000" img height="250" alt="image" src="https://user-images.githubusercontent.com/120063554/206932234-95e796a6-ced0-4f47-ac4b-dbc534cf97fa.png">

## Query Testing

After creating these tables and populating with sample data, we perform a quick query test to ensure that data is being pulled correctly. For example, we could write the following code if we were curious to see the status of complaints and which sales rep is handling it:

```sql
SELECT c.description, c.status, s.first_name|| ' ' || s.last_name "Sales Rep"
FROM z_complaint c JOIN z_sales_rep s ON (c.rep_id = s.id))
```
This query would yield the following:

<img width="1000" img height="100" alt="image" src="https://user-images.githubusercontent.com/120063554/206932549-fd26d528-e549-4acc-bbfe-3bc91d475d1e.png">

## Recommendations

We have successfully created a centralized database along with logical relationships and tables. However, there is always room for improvement. We have accomplished the main objective, but we believe there are some points we can add or improve upon. To further increase functionality, we would recommend the following:

- Increase the scope of complaints to the individual level
- Include the ability to pre-order items for a certain date
- Institute a membership option with special deals and sales
- Create an item menu and a promotional menu
- A commission bonus for sales reps that net bigger payouts

## Conclusion

Our consulting team has successfully implemented a comprehensive database that keeps track of orders, customers, historical data, and much more. Our database will allow Zerious Zoccer Zone to meet the increased logistical demands of the growing soccer industry and the increasing popularity. 


