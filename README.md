# Database-Management-Final-
# Book Management System Database

## Project Overview
A comprehensive MySQL relational database designed to manage books, authors, publishers, sales, and inventory for a bookstore or library system. This database implements a real-world business case with proper relationships, constraints, views, triggers, and stored procedures to handle all aspects of book management.

## Description
The Book Management System database provides a complete solution for managing:
- Books and their detailed information
- Authors and publishers
- Book categories with hierarchical relationships
- Inventory tracking with automated stock management
- Customer information and sales records
- Book reviews and ratings

The system features properly implemented relationships (one-to-one, one-to-many, many-to-many), constraints (primary keys, foreign keys, unique constraints), and includes business logic through triggers and stored procedures.

## ERD (Entity Relationship Diagram)

![Book Management System ERD](https://i.imgur.com/rTMxPOX.png)

*Note: If the image above doesn't load, please view the ERD.png file in this repository.*

## Database Structure

### Key Tables
- **books**: Core table containing book information
- **authors**: Information about book authors
- **publishers**: Book publishing companies
- **categories**: Book genres/categories with hierarchical structure
- **inventory**: Tracks book stock levels
- **customers**: Customer information
- **sales** & **sale_items**: Tracks book sales transactions
- **reviews**: Customer reviews and ratings for books

### Relationship Tables
- **book_authors**: Many-to-many relationship between books and authors
- **book_categories**: Many-to-many relationship between books and categories

### Advanced Features
- **Triggers**: Automatically update inventory when sales occur
- **Views**: For common complex queries (book details, sales reporting, low stock alerts)
- **Stored Procedures**: Handle business operations like restocking
- **Functions**: Calculate metrics like total revenue

## Setup Instructions

### Prerequisites
- MySQL Server 5.7+ or MySQL 8.0+
- MySQL client or MySQL Workbench

### Installation Steps
1. Download the `book_management_system.sql` file from this repository
2. Open MySQL client or MySQL Workbench
3. Connect to your MySQL server
4. Execute the SQL script:
   - In MySQL Workbench: File > Open SQL Script > Select the .sql file > Execute
   - In MySQL command line: `mysql -u username -p < book_management_system.sql`

The script will:
- Create a new database called `book_management_system`
- Create all required tables with proper constraints
- Set up views, triggers, and stored procedures
- Insert sample data for testing

### Testing the Database
After running the script, you can test the database with queries like:

```sql
-- View all books with their details
SELECT * FROM book_details;

-- Check inventory levels
SELECT * FROM inventory;

-- View sales information
SELECT * FROM sales_report;

-- Identify books with low stock
SELECT * FROM low_stock_books;

-- Calculate revenue for a specific period
SELECT get_total_revenue('2023-01-01', '2023-12-31') AS annual_revenue;
```

## Technical Implementation Details

### Primary Key Implementation
All tables use auto-incrementing integer primary keys for efficient indexing and relationships.

### Foreign Key Implementation
Foreign keys enforce referential integrity with appropriate ON DELETE and ON UPDATE actions:
- CASCADE where child records should follow parent changes
- RESTRICT where deletion should be prevented if references exist
- SET NULL where appropriate for optional relationships

### Constraints
- NOT NULL constraints on required fields
- UNIQUE constraints to prevent duplicate entries
- CHECK constraints to validate data (e.g., ratings between 1-5)

### Timestamps
All tables include created_at/updated_at timestamps to track record history.

## Future Enhancements
Potential extensions to this database could include:
- Book borrowing functionality for library use cases
- Supplier and purchasing order management
- Employee access control and sales tracking
- E-book vs physical book distinction
- Loyalty program tracking

## Author
Gladwell Nduta


## License
This project is available for educational purposes.
