# Zerious Zoccer Zone Project

## Introduction

**SITUATION**

This was the final project in my first SQL class I took. This project revolves around a soccer equipment store, named Zerious Zoccer Zone. The store business is rapidly growing, and hires our consulting team to create a centralized database in order to handle incoming information. They have certain requirements regarding order placing, inventory tracking, and customer information records. 

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


<img width="1000" img height="500" alt="image" src="https://user-images.githubusercontent.com/120063554/206881857-4459cda0-60bb-4220-b277-e391a789b4f5.png">


## Visualization



