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



## Data Cleanup

Next step, I decided to practice with SQL. I created a table with columns that I thought I needed. Then, I combined the two box office sources into one file in Excel, and imported the data into SQL through a bulk insert. The code and results for these steps are provided below:

```sql
CREATE TABLE MCU (
ID int IDENTITY(1,1) PRIMARY KEY,
Title varchar(200),
Director varchar(200),
ReleaseDate date,
Budget bigint,
OpeningWeekend bigint,
DomesticBoxOffice bigint,
WorldwideBoxOffice bigint,
OpeningTheaters bigint,
Distributor varchar(200)
)

BULK INSERT MCU
FROM 'C:\Users\larry\Desktop\Projects\MCU1.csv'
WITH (FIRSTROW = 2,
    FIELDTERMINATOR = ',',
    ROWTERMINATOR='\n',
    BATCHSIZE=250000,
    MAXERRORS=2);

SELECT *
FROM MCU
```

<img width="1000" img height="500" alt="image" src="https://user-images.githubusercontent.com/120063554/206881857-4459cda0-60bb-4220-b277-e391a789b4f5.png">

The next step was to connect all my data sources to Power BI. From the Wikipedia source, I imported the critical reception, Infinity Saga, and Multiverse Saga tables. 

## Visualization

After connecting all the data sources to Power BI, I had to make a few edits to the tables I needed. First, I created one large table, named "All Phases", by combining the "Infinity Saga" and "Multiverse Saga" tables from the Wikipedia source. Then, I made a 1:1 connection between the "All Phases" table and the critical reception table and SQL table. Once these connections were made, all I had to do was create a few measures and begin visualization. Feel free to check out the dashboard on my Notion page!

