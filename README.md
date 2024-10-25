# whole-sale-management-system-database-

Here’s a summary of the new tables you've added to the eCommerce database, along with key points and a breakdown of primary and foreign keys.

### Summary of New Schema

1. **Database Name**: `ecommerces_db` (continuation from previous tables)

2. **New Tables**:
   - **Buyer**
     - Stores information about suppliers.
     - **Key Fields**:
       - `buyer_id`: Primary Key
       - `buyer_name`: Name of the supplier
       - `contact_info`: Supplier's contact details
       - `address`: Supplier's address

   - **Stock**
     - Keeps track of stock items and their suppliers.
     - **Key Fields**:
       - `stock_id`: Primary Key
       - `item_name`: Name of the stock item
       - `quantity`: Quantity in stock
       - `purchase_date`: Date of purchase
       - `supplier_id`: Foreign Key referencing `Buyer(buyer_id)`

   - **Customer**
     - Contains customer information.
     - **Key Fields**:
       - `customer_id`: Primary Key
       - `customer_name`: Name of the customer
       - `contact_info`: Customer's contact details
       - `address`: Customer's address

   - **Payment**
     - Manages payment details made by customers.
     - **Key Fields**:
       - `payment_id`: Primary Key
       - `customer_id`: Foreign Key referencing `Customer(customer_id)`
       - `amount_paid`: Amount paid by the customer
       - `payment_status`: Status of the payment (e.g., Paid, Pending)
       - `payment_date`: Date of the payment

   - **ProfitCalculation**
     - Records profit details for each month.
     - **Key Fields**:
       - `profit_id`: Primary Key
       - `month`: Month for profit calculation
       - `total_sales`: Total sales for the month
       - `total_cost`: Total costs for the month
       - `profit`: Profit for the month

### Key Points

- **Relationships**:
  - A **Buyer** can supply multiple items in **Stock** (one-to-many).
  - A **Customer** can have multiple **Payments** (one-to-many).

- **Data Integrity**: Foreign keys ensure that stock items are linked to valid suppliers and payments are linked to valid customers.

- **Profit Tracking**: The `ProfitCalculation` table allows for easy monitoring of monthly profits, aiding in financial management.

### Keys Summary

- **Primary Keys**:
  - `Buyer`: `buyer_id`
  - `Stock`: `stock_id`
  - `Customer`: `customer_id`
  - `Payment`: `payment_id`
  - `ProfitCalculation`: `profit_id`

- **Foreign Keys**:
  - `Stock`: `supplier_id` references `Buyer(buyer_id)`
  - `Payment`: `customer_id` references `Customer(customer_id)`

This structure enhances the eCommerce database by incorporating supplier and stock management alongside customer payment processing and profit calculation, providing a comprehensive view of the business's operations. If you need more details or assistance, just let me know!
