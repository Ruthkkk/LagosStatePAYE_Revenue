# LagosStatePAYE_Revenue
# Lagos State is one of the top revenue generating states in Nigeria and one of the country's highest tax earner. Details show that in the 2021 financial year, the state earned N390.406 billion in tax as a component of its Internally Generated Revenue (IGR). As of the second quarter of 2022, the state earned N256.130 billion in personal income tax. 

# I got my hands dirty with some data from January 2023 - August 2023) and i decided to analyze the data below::

# All the data in the table

SELECT *
FROM paye_data;

# Total Revenue Analysis
# What is the total revenue collected 

SELECT SUM(Cr_Amount) AS TotalRevenue
FROM paye_data;

# Top Agencies
# What is the revenue share contributed by the top 5 agencies?

SELECT TOP 5 Agency_Name, SUM(Cr_Amount) AS TotalRevenue
FROM paye_data
GROUP BY Agency_Name
ORDER BY TotalRevenue DESC;

# How many entries does the top agency have?

SELECT TOP 1 Agency_Name, COUNT(EntryID) AS EntryCount
FROM paye_data
GROUP BY Agency_Name
ORDER BY EntryCount DESC;

# Revenue Distribution
# What is the distribution of revenue across different revenue codes?

SELECT Revenue_Code, SUM(Cr_Amount) AS TotalRevenue
FROM paye_data
GROUP BY Revenue_Code
ORDER BY TotalRevenue DESC;

# Which revenue code has the highest total revenue?

SELECT TOP 1 Revenue_Code, SUM(Cr_Amount) AS TotalRevenue
FROM paye_data
GROUP BY Revenue_Code
ORDER BY TotalRevenue DESC;

# What is the distribution of revenue across different Agencies?

SELECT Agency_Name, SUM(Cr_Amount) AS TotalRevenue
FROM paye_data
GROUP BY Agency_Name
ORDER BY TotalRevenue DESC;

# Top Transactions
# Which top 3 transactions has the highest credit (Cr Amount)?

SELECT TOP 3 EntryID, Agency_Name, Cr_Amount, Revenue_Name
FROM paye_data
ORDER BY Cr_Amount DESC;

# Revenue Name Breakdown:
# What is the total revenue for each revenue name?

SELECT Revenue_Name, SUM(Cr_Amount) AS TotalRevenue
FROM paye_data
GROUP BY Revenue_Name
ORDER BY TotalRevenue DESC;

# Highest and Lowest PAYE amount

SELECT MAX(Cr_Amount) AS HighestPaymentAmount, MIN(Cr_Amount) AS LowestPaymentAmount
FROM paye_data;















