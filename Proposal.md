# Prime

## Proposal

A tool that helps a business keep track of computer repair work orders and technicians working on them. This tool will work against its own database, with the ability to scrape and push data to and from a propeprietary backend. It will use the Teckst API to allow SMS-based communication between the business and the customer, all within a single and easy to use React app.

## Tech Stack

This tool aims to use React, Redux, Node, Router, Postgres. Additional tools include xml2js for parsing legacy XML data, and react-bootstrap for styling.

This aims to be a proprietary website for a business, and will be used by a small team of engineers to facilitate communication between customers and their respective technicians, with robust note-taking and on-the-fly event logging at their fingertips.

The data being recorded will be in the form of a work order, with the following fields:

1. Customer Name
2. Customer ID
3. Unit serial number
4. Customer Phone Number
5. Last time customer backed up their computer's data
6. Customer's anti-virus solution
7. Customer's preferred way of communication
8. Customer's computer model number

This will be scraped from an external API as well as generated from within our fields at the time of check-in.

## Schema

The database schema will consist of the following tables and fields:

Work Order (id PK, customer_id, last_backup_date, anti_virus_solution, preferred_communication, computer_model_number, technician_id fk, status, is_in_history)

Customer (id PK, Name, Phone Number, Email, Address, City, State, Zip, Notes)

Technician (name, id, session_key)

Customer_Orders(FK customer_id, FK work_order_id)

Work Order Interactions (FK work_order_id, message, technician_id)

## Security

User authentication will be handled by the external API. Only authorized users can use the tool.