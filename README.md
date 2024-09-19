# BBT3104-Lab1of6-DatabaseTransactions


| **Key**                                                               | Value                                                                                                                                                                              |
|---------------|---------------------------------------------------------|
| **Group Name**                                                               | ? |
| **Semester Duration**                                                 | 19<sup>th</sup> August - 25<sup>th</sup> November 2024                                                                                                                       |

## Flowchart



## Pseudocode

// Step 1: Create a new order
orderNumber = generateNewOrderNumber()
INSERT INTO orders (orderNumber, orderDate, requiredDate, shippedDate, status, customerNumber)
VALUES (orderNumber, currentDate(), requiredDate(3 days later), shippedDate(2 days later), 'In Process', 145)

// Step 2: Create Savepoint before adding Product 1
SAVEPOINT before_product_1

// Step 3: Insert Product 1 and update stock
INSERT INTO orderdetails (orderNumber, productCode, quantityOrdered, priceEach, orderLineNumber)
VALUES (orderNumber, 'S18_1749', 2724, 136, 1)
quantityInStock = SELECT quantityInStock FROM products WHERE productCode = 'S18_1749'
UPDATE products SET quantityInStock = quantityInStock - 2724 WHERE productCode = 'S18_1749'

// Step 4: Create Savepoint before adding Product 2
SAVEPOINT before_product_2

// Step 5: Insert Product 2 and update stock
INSERT INTO orderdetails (orderNumber, productCode, quantityOrdered, priceEach, orderLineNumber)
VALUES (orderNumber, 'S18_2248', 540, 55.09, 2)
quantityInStock = SELECT quantityInStock FROM products WHERE productCode = 'S18_2248'
UPDATE products SET quantityInStock = quantityInStock - 540 WHERE productCode = 'S18_2248'

// Step 6: Rollback to Savepoint 2 if there's an error with Product 2
IF error THEN
    ROLLBACK TO SAVEPOINT before_product_2
ENDIF

// Step 7: Create Savepoint before adding Product 3
SAVEPOINT before_product_3

// Step 8: Insert Product 3 and update stock
INSERT INTO orderdetails (orderNumber, productCode, quantityOrdered, priceEach, orderLineNumber)
VALUES (orderNumber, 'S12_1099', 68, 95.34, 3)
quantityInStock = SELECT quantity

## Support for the Sales Departments' Report
