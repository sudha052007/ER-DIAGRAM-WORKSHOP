# ER-DIAGRAM-WORKSHOP
SUDHARSHINI.G
212225220106
## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.
# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
 <img width="1637" height="717" alt="image" src="https://github.com/user-attachments/assets/fe631a04-6fd8-4f59-b52c-f67c3a54309c" />


### Entities and Attributes
CUSTOMER: CUSTOMER ID (Primary Key), NAME, CONTACT DETAILS, TABLENUMBER.   
TABLE: TABLE ID (Primary Key), STATUS, LOCATION.   
WAITER: WAITER ID (Primary Key), NAME, CONTACT DETAILS.   
ORDER: ORDER ID (Primary Key), DATETIME, TOTALAMOUNT, STATUS, along with foreign keys referencing Table, Waiter, and Supervisor.   
ORDER ITEM: ORDER ITEM ID (Primary Key), ORDER ID (Foreign Key), FOOD ITEM ID (Foreign Key), QUANTITY, STATUS.   
FOOD ITEM: FOOD ITEM ID (Primary Key), NAME, DESCRIPTION, PRICE, CATEGORY.   
CHEF: CHEF ID (Primary Key), CHEF NAME, CHEF CONTACT DETAILS.   
BILL: BILL ID (Primary Key), ORDER ID (Foreign Key), TOTAL AMOUNT, PAYMENT STATUS.   
SUPERVISOR: SUPERVISOR ID (Primary Key), NAME, CONTACT DETAILS.   

### Relationships and Constraints
has (Customer and Table): Connects customers to their dining tables.   
serves (Waiter and Table): One-to-many relationship where a waiter can serve multiple tables.   creates (Waiter and Order): One-to-many relationship where waiters generate orders for customers.   manages (Supervisor and Order): Supervisors oversee and manage restaurant orders.   
contains (Order and Order Item): One-to-many relationship where a single order consists of multiple individual order items.   
refers to (Order Item and Food Item): Each order item points back to a specific menu food item.   prepares (Chef and Order Item): Kitchen staff prepare the ordered items.   generates (Order and Bill): One-to-one relationship where a completed order produces a bill for payment.   


### Assumptions
- Each order can contain multiple food items broken down as individual Order Items with specific quantities and preparation statuses.

-A Bill is generated directly from an Order once dining is complete, tracking the payment status and total amount.

-Table Numbers and customer details help map which customer or party is seated at a particular Table ID.
 

---
