# Library Management System Backend API

This project is a Library Management System Backend API developed using Python and Flask, with MariaDB as the database. The API allows for CRUD operations on books, borrowers, and transactions. The project also implements authentication using JWT, advanced search operations, and robust error handling.

## Project Setup

### Prerequisites

- Python 3.x
- Flask
- Flask-MySQLdb
- MariaDB

### Installation

1. *Clone the repository:*

    bash
    https://github.com/kumkumtiwari798/library-management-system.git
    cd library-management-system
    

3. *Create a virtual environment and activate it:*

    bash
    python -m venv venv
    source venv/bin/activate   # On Windows, use `venv\Scripts\activate`
    

4. *Install the dependencies:*

    bash
    pip install -r requirements.txt
    

5. *Configure MariaDB:*

    - Install MariaDB and create a database named library_db.
    - Create a user for the database and grant necessary permissions.

    sql
    CREATE DATABASE library_db;
    CREATE USER 'library_user'@'localhost' IDENTIFIED BY 'your_password';
    GRANT ALL PRIVILEGES ON library_db.* TO 'library_user'@'localhost';
    FLUSH PRIVILEGES;
    

6. *Update the configuration:*

    Update the MySQL configuration in app.py:

    python
    app.config['MYSQL_HOST'] = 'localhost'
    app.config['MYSQL_USER'] = 'library_user'
    app.config['MYSQL_PASSWORD'] = 'admin'
    app.config['MYSQL_DB'] = 'library_db'
    

### Database Schema

The database schema includes the following tables:

- *books*
- *borrowers*
- *transactions*

### Running the Application

1. *Start the Flask application:*

    bash
    python3 app.py
    

2. *Access the API:*

    The API will be accessible at http://127.0.0.1:5000/.

## API Endpoints

### Books

- *GET /books*
    - Retrieve all books.
- *POST /books*
    - Add a new book.
    - Request Body: { "title": "Book Title", "author": "Author Name", "published_date": "YYYY-MM-DD" }
- *GET /books/<int:id>*
    - Retrieve a book by ID.
- *PUT /books/<int:id>*
    - Update a book by ID.
    - Request Body: { "title": "Updated Title", "author": "Updated Author", "published_date": "YYYY-MM-DD" }
- *DELETE /books/<int:id>*
    - Delete a book by ID.

### Borrowers

- *GET /borrowers*
    - Retrieve all borrowers.
- *POST /borrowers*
    - Add a new borrower.
    - Request Body: { "name": "Borrower Name", "contact": "Contact Info" }
- *GET /borrowers/<int:id>*
    - Retrieve a borrower by ID.
- *PUT /borrowers/<int:id>*
    - Update a borrower by ID.
    - Request Body: { "name": "Updated Name", "contact": "Updated Contact" }
- *DELETE /borrowers/<int:id>*
    - Delete a borrower by ID.

### Transactions

- *GET /transactions*
    - Retrieve all transactions.
- *POST /transactions*
    - Add a new transaction.
    - Request Body: { "book_id": int, "borrower_name": "Borrower Name", "borrow_date": "YYYY-MM-DD" }
- *GET /transactions/<int:id>*
    - Retrieve a transaction by ID.
- *PUT /transactions/<int:id>*
    - Update a transaction by ID.
    - Request Body: { "book_id": int, "borrower_name": "Updated Borrower", "borrow_date": "YYYY-MM-DD", "transaction_date": "YYYY-MM-DD" }
- *DELETE /transactions/<int:id>*
    - Delete a transaction by ID.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request.

## Contact

For any questions or feedback, please reach out at 

kumkumtiwari798@gmail.com.
