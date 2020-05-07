# SQL

create database retail;

use retail;

CREATE TABLE IF NOT EXISTS salespeople (
 snum INT NOT NULL,
 sname VARCHAR(30) NOT NULL,
 city VARCHAR(30) NOT NULL,
 comm DECIMAL(4,2) NOT NULL,
 PRIMARY KEY (snum)
 );
 
INSERT INTO salespeople VALUES (1001, 'Peel', 'London', 0.12),(1002,Serres,San Jose, .13),(1004,Motika,London,.11),
(1007,Rifkin,Barcelona,.15),(1003,AxelRod,New York,.10),(1005,Fran,London,.26);


CREATE TABLE IF NOT EXISTS customer (
 cnum INT NOT NULL,
 cname VARCHAR(30) NOT NULL,
 city VARCHAR(30) NOT NULL,
 rating int not null,
snum int NOT NULL,
 PRIMARY KEY (cnum),
 FOREIGN KEY (snum) REFERENCES salespeople(snum)
 );
 
INSERT INTO customer VALUES (2001, 'Hoffman', 'London',100, 1001);(2002,Giovanni,Rome,200,1003)(2003,Liu San,Jose,200,1002)
(2004,Grass,Berlin,300,1002)(2006,Clemens,London,100,1001)(2008,Cisneros,San Jose,300,1007)(2007,Pereira,Rome,100,1004)

CREATE TABLE IF NOT EXISTS orders (
 onum INT NOT NULL,
 amt DECIMAL(7,2) NOT NULL,
 odate Date NOT NULL,
cnum int NOT NULL,
 PRIMARY KEY (onum),
 FOREIGN KEY (cnum) REFERENCES customer(cnum)
 );
 
INSERT INTO orders VALUES (3001, 18.69, '1996-03-10', 2008),(3003,767.19,'10/03/96',2001),
(3002,1900.10,'10/03/96',2007),(3005,5160.45,'10/03/96',2003),(3006,1098.16,'10/03/96',2008),
(3009,1713.23,'10/04/96',2002),(3007,75.75,'10/04/96',2002),(3008,4723.00,'10/05/96',2006),(3010,1309.95,'10/06/96',2004)
(3011,9891.88,'10/06/96',2006)


show tables ;

describe orders;

Update clause
UPDATE table_name SET field1=new-value1, field2=new-value2
[WHERE Clause]

Delete clause

DELETE FROM table_name [WHERE Clause]

Queries

1. List all the columns of the Salespeople table.

2. List all customers with a rating of 100.

3. Find all records in the Customer table with NULL values in the city column.

4. Find the largest order taken by each salesperson on each date.

5. Arrange the Orders table by descending customer number.

6. Find which salespeople currently have orders in the Orders table.

7. List names of all customers matched with the salespeople serving them.

8. Find the names and numbers of all salespeople who had more than one customer.

9. Count the orders of each of the salespeople and output the results in descending order.

10. List the Customer table if and only if one or more of the customers in the Customer table are
located in San Jose.

11. Match salespeople to customers according to what city they lived in.

12. Find the largest order taken by each salesperson.

13. Find customers in San Jose who have a rating above 200.

14. List the names and commissions of all salespeople in London.

15. List all the orders of salesperson Motika from the Orders table.

16. Find all customers with orders on October 3.

17. Give the sums of the amounts from the Orders table, grouped by date, eliminating all those
dates where the SUM was not at least 2000.00 above the MAX amount.

18. Select all orders that had amounts that were greater than at least one of the orders from
October 6.

19. Write a query that uses the EXISTS operator to extract all salespeople who have customers
with a rating of 300.

20. Find all pairs of customers having the same rating.

21. Find all customers whose CNUM is 1000 above the SNUM of Serres.

22. Give the salespeople’s commissions as percentages instead of decimal numbers.

23. Find the largest order taken by each salesperson on each date, eliminating those MAX orders
which are less than $3000.00 in value.

24. List the largest orders for October 3, for each salesperson.

25. Find all customers located in cities where Serres (SNUM 1002) has customers.

26. Select all customers with a rating above 200.00.

27. Count the number of salespeople currently listing orders in the Orders table.

28. Write a query that produces all customers serviced by salespeople with a commission above
12%. Output the customer’s name and the salesperson’s rate of commission.

29. Find salespeople who have multiple customers.

30. Find salespeople with customers located in their city.

31. Find all salespeople whose name starts with ‘P’ and the fourth character is ‘l’.

32. Write a query that uses a subquery to obtain all orders for the customer named Cisneros.
Assume you do not know his customer number.

33. Find the largest orders for Serres and Rifkin.

34. Extract the Salespeople table in the following order : SNUM, SNAME, COMMISSION, CITY.

35. Select all customers whose names fall in between ‘A’ and ‘G’ alphabetical range.

36. Select all the possible combinations of customers that you can assign.

37. Select all orders that are greater than the average for October 4.

38. Write a select command using a corelated subquery that selects the names and numbers of all
customers with ratings equal to the maximum for their city.

39. Write a query that totals the orders for each day and places the results in descending order.

40. Write a select command that produces the rating followed by the name of each customer in
San Jose.

41. Find all orders with amounts smaller than any amount for a customer in San Jose.

42. Find all orders with above average amounts for their customers.

43. Write a query that selects the highest rating in each city.

44. Write a query that calculates the amount of the salesperson’s commission on each order by a
customer with a rating above 100.00.

45. Count the customers with ratings above San Jose’s average.

46. Write a query that produces all pairs of salespeople with themselves as well as duplicate rows
with the order reversed.

47. Find all salespeople that are located in either Barcelona or London.

48. Find all salespeople with only one customer.

49. Write a query that joins the Customer table to itself to find all pairs of customers served by a
single salesperson.

50. Write a query that will give you all orders for more than $1000.00

51. Write a query that lists each order number followed by the name of the customer who made
that order.

52. Write 2 queries that select all salespeople (by name and number) who have customers in their
cities who they do not service, one using a join and one a corelated subquery. Which solution
is more elegant?

53. Write a query that selects all customers whose ratings are equal to or greater than ANY (in the
SQL sense) of Serres’?

54. Write 2 queries that will produce all orders taken on October 3 or October 4.

55. Write a query that produces all pairs of orders by a given customer. Name that customer and
eliminate duplicates.

56. Find only those customers whose ratings are higher than every customer in Rome.

57. Write a query on the Customers table whose output will exclude all customers with a rating <=
100.00, unless they are located in Rome.

58. Find all rows from the Customers table for which the salesperson number is 1001.

59. Find the total amount in Orders for each salesperson for whom this total is greater than the
amount of the largest order in the table.

60. Write a query that selects all orders save those with zeroes or NULLs in the amount field.

61. Produce all combinations of salespeople and customer names such that the former precedes
the latter alphabetically, and the latter has a rating of less than 200.

62. List all Salespeople’s names and the Commission they have earned.

63. Write a query that produces the names and cities of all customers with the same rating as
Hoffman. Write the query using Hoffman’s CNUM rather than his rating, so that it would still be
usable if his rating changed.

64. Find all salespeople for whom there are customers that follow them in alphabetical order.

65. Write a query that produces the names and ratings of all customers of all who have above
average orders.

66. Find the SUM of all purchases from the Orders table.

67. Write a SELECT command that produces the order number, amount and date for all rows in
the order table.

68. Count the number of nonNULL rating fields in the Customers table (including repeats).

69. Write a query that gives the names of both the salesperson and the customer for each order
after the order number.

70. List the commissions of all salespeople servicing customers in London.

71. Write a query using ANY or ALL that will find all salespeople who have no customers located in
their city.

72. Write a query using the EXISTS operator that selects all salespeople with customers located in
their cities who are not assigned to them.

73. Write a query that selects all customers serviced by Peel or Motika. (Hint : The SNUM field
relates the two tables to one another.)

74. Count the number of salespeople registering orders for each day. (If a salesperson has more
than one order on a given day, he or she should be counted only once.)

75. Find all orders attributed to salespeople in London.

76. Find all orders by customers not located in the same cities as their salespeople.

77. Find all salespeople who have customers with more than one current order.

78. Write a query that extracts from the Customers table every customer assigned to a
salesperson who currently has at least one other customer (besides the customer being
selected) with orders in the Orders table.

79. Write a query that selects all customers whose names begin with ‘C’.

80. Write a query on the Customers table that will find the highest rating in each city. Put the output
in this form : for the city (city) the highest rating is : (rating).

81. Write a query that will produce the SNUM values of all salespeople with orders currently in the
Orders table (without any repeats).

82. Write a query that lists customers in descending order of rating. Output the rating field first,
followed by the customer’s names and numbers.

83. Find the average commission for salespeople in London.

84. Find all orders credited to the same salesperson who services Hoffman (CNUM 2001).

85. Find all salespeople whose commission is in between 0.10 and 0.12 (both inclusive).

86. Write a query that will give you the names and cities of all salespeople in London with a
commission above 0.10.

87. What will be the output from the following query?
SELECT * FROM ORDERS
where (amt < 1000 OR NOT (odate = 10/03/1996 AND cnum >
2003));

88. Write a query that selects each customer’s smallest order.

89. Write a query that selects the first customer in alphabetical order whose name begins with G.

90. Write a query that counts the number of different nonNULL city values in the Customers table.

91. Find the average amount from the Orders table.

92. What would be the output from the following query?
SELECT * FROM ORDERS
WHERE NOT (odate = 10/03/96 OR snum > 1006) AND amt >=
1500);

93. Find all customers who are not located in San Jose and whose rating is above 200.

94. Give a simpler way to write this query :
SELECT snum, sname city, comm FROM salespeople
WHERE (comm > + 0.12 OR comm < 0.14);

95. Evaluate the following query :
SELECT * FROM orders
WHERE NOT ((odate = 10/03/96 AND snum > 1002) OR amt > 2000.00);

96. Which salespersons attend to customers not in the city they have been assigned to?

97. Which salespeople get commission greater than 0.11 are serving customers rated less than
250?

98. Which salespeople have been assigned to the same city but get different commission
percentages?

99. Which salesperson has earned the most by way of commission?

100.Does the customer who has placed the maximum number of orders have the maximum rating?

101.Has the customer who has spent the largest amount of money been given the highest rating?

102.List all customers in descending order of customer rating.

103.On which days has Hoffman placed orders?

104.Do all salespeople have different commissions?

105.Which salespeople have no orders between 10/03/1996 and 10/05/1996?

106.How many salespersons have succeeded in getting orders?

107.How many customers have placed orders?

108.On which date has each salesperson booked an order of maximum value?

109.Who is the most successful salesperson?

110.Who is the worst customer with respect to the company?

111.Are all customers not having placed orders greater than 200 totally been serviced by
salespersons Peel or Serres?

112.Which customers have the same rating?

113.Find all orders greater than the average for October 4th.

114.Which customers have above average orders?

115.List all customers with ratings above San Jose’s average.

116.Select the total amount in orders for each salesperson for whom the total is greater than the
amount of the largest order in the table.

117.Give names and numbers of all salespersons who have more than one customer.

118.Select all salespersons by name and number who have customers in their city whom they
don’t service.

119.Which customers’ rating should be lowered?

120.Is there a case for assigning a salesperson to Berlin?

121.Is there any evidence linking the performance of a salesperson to the commission that he or
she is being paid?

122.Does the total amount in orders by customer in Rome and London exceed the commission
paid to salespersons in London and New York by more than 5 times?

123.Which is the date, order number, amt and city for each salesperson (by name) for the
maximum order he has obtained?

124.Which salesperson(s) should be fired?

125.What is the total income for the company?
