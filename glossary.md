# Glossary/Data Dictionary

| **_Entity_** | **_Attribute_**        | **_Data Type_** | **_Description_**                                     | **_Constraints_** |                                       
|:-------------|------------------------|-----------------|-------------------------------------------------------|:------------------|
| **Product**  | product_id             | INTEGER         | Unique identifier for the product                     | Primary Key       |
|              | product_name           | VARCHAR(255)    | Name of the product                                   |                   |
|              | BOM(Bill of Materials) | VARCHAR(255)    | Listing the components of the product                 |                   |
|              | production_time        | FLOAT           | Time (in hours) needed to produce this product        |                   |
|              | variant                | VARCHAR(255)    | Specific variant of the product (e.g., size, color)   |                   |
|              | category               | VARCHAR(255)    | Category of the product (e.g., furniture, metalwork)  |                   |



| **_Entity_** | **_Attribute_** | **_Data Type_** | **_Description_**                                                         | **_Constraints_**         |                                       
|:-------------|-----------------|-----------------|---------------------------------------------------------------------------|:--------------------------|
| **Order**    | order_id        | INTEGER         | Unique identifier for the order                                           | Primary Key               |
|              | customer_id     | INTEGER         | Identifier of the customer who placed the order                           | Foreign Key from Customer |
|              | order_date      | DATE            | Date the order was placed                                                 |                           |
|              | delivery_date   | DATE            | Expected delivery date for the order                                      |                           |
|              | total_quantity  | INTEGER         | Total number of products in the order                                     |                           |
|              | order_status    | VARCHAR(255)    | Status of the order (e.g., Placed,Confirmed,Shipped, Completed,Cancelled) |                           |




| **_Entity_** | **_Attribute_** | **_Data Type_** | **_Description_**                                                 | **_Constraints_**        |                                       
|:-------------|-----------------|-----------------|-------------------------------------------------------------------|:-------------------------|
| **Customer** | customer_id     | INTEGER         | Unique identifier for the customer                                | Primary Key              |
|              | customer_name   | VARCHAR(255)    | Identifier of the customer who placed the order                   |                          |
|              | NIF             | INTEGER         | Tax identification number (NIF) of the customer                   |                          |
|              | phone_number    | INTEGER         | Phone number of the customer                                      |                          |
|              | email           | VARCHAR(255)    | Email of the customer                                             |                          |
|              | customer_type   | VARCHAR(255)    | Type of customer (Individual/Company)                             |                          |
|              | address         | VARCHAR(255)    | Address of the customer                                           |                          |




| **_Entity_** | **_Attribute_** | **_Data Type_** | **_Description_**                                                                         | **_Constraints_**                               |                                       
|:-------------|-----------------|-----------------|-------------------------------------------------------------------------------------------|:------------------------------------------------|
| **Payment**  | payment_id      | INTEGER         | Unique identifier for the payment                                                         | Primary Key                                     |
|              | order_id        | INTEGER         | Unique identifier for the order                                                           | Foreign Key from Order originally from Customer |
|              | customer_id     | INTEGER         | Unique identifier for the customer                                                        | Foreign Key from Customer                       |
|              | payment_status  | VARCHAR(255)    | Status of the payment (e.g., Failed,Confirmed,Pending)                                    | Primary Key                                     |
|              | payment_method  | VARCHAR(255)    | Method of payment (e,g.,VISA,debit card,mbAway,etc...,all other accepted forms of payment |                                                 |
|              | card_number     | Integer         | The 16-digit number on the front of the card.                                             |                                                 |
|              | CVV/CVC         | INTEGER         | The 3-4 digit security code on the back of the card.                                      |                                                 |
|              | cardholder_name | VARCHAR(255)    | The name on the credit/debit card.                                                        |                                                 |
|              | expiration_date | VARCHAR(255)    | The card's expiration date (MM/YY).                                                       |                                                 |
|              | billing_address | VARCHAR(255)    | The address associated with the card to verify the payment.                               |                                                 |
|              | amount          | Float           | The total payment amount, including any taxes and shipping costs.                         |                                                 |




| **_Entity_** | **_Attribute_** | **_Data Type_** | **_Description_**                                 | **_Constraints_**        |                                       
|:-------------|-----------------|-----------------|---------------------------------------------------|:-------------------------|
| **Machine**  | machine_id      | INTEGER         | Unique identifier for the customer                | Primary Key              |
|              | machine_name    | VARCHAR(255)    | Name of the machine                               |                          |
|              | operation_type  | VARCHAR(255)    | Tax identification number (NIF) of the customer   |                          |
|              | processing_time | FLOAT           | Time (in hours) to complete an operation          |                          |
|              | machine_status  | VARCHAR(255)    | Status of the machine (e.g., Active, Maintenance) |                          |




| **_Entity_**  | **_Attribute_** | **_Data Type_** | **_Description_**                                 | **_Constraints_**        |                                       
|:--------------|-----------------|-----------------|---------------------------------------------------|:-------------------------|
| **Operation** | machine_id      | INTEGER         | Unique identifier for the customer                | Primary Key              |
|               | machine_name    | VARCHAR(255)    | Name of the machine                               |                          |
|               | operation_type  | VARCHAR(255)    | Tax identification number (NIF) of the customer   |                          |
|               | processing_time | FLOAT           | Time (in hours) to complete an operation          |                          |
|               | machine_status  | VARCHAR(255)    | Status of the machine (e.g., Active, Maintenance) |                          |
