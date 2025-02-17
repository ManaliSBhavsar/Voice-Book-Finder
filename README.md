# Voice-Book-Finder

Voice Book Finder is a full-fledged library management system with functionalities to add, search, delete, and issue books. Speech recognition is incorporated to search for books by genre, providing a user-friendly interface for book management. Deployed on local systems, demonstrating database connection, GUI design, and interactive features. Integrated into a MySQL database to store book and user details and performed CRUD operations using Python. For enhanced security, the system implements email and password authentication for both students and admins. This ensures secure access to the system for different user roles.

# Tech Stack used
Python: The main programming language used to develop the application.
Tkinter: A Python library for creating graphical user interfaces (GUIs). It's used to design the login screens, forms for adding and removing books, and buttons.
Speech Recognition (SpeechRecognition): The library used for voice-based book searching. It uses Google's Web Speech API to recognize speech.
MySQL (PyMySQL): A MySQL database is used for storing book details, user information, and tracking issued books. The pymysql library is used to interact with the database.
SMTP (smtplib): Used for sending emails (e.g., when a book is issued to a user).
OS: A standard library for interacting with the file system, such as checking if a user file exists for login purposes.

## Database Setup

The database integration is part of the full implementation, but is excluded from the GitHub repository for simplicity. Offer details on how to set it up locally.

1. Install MySQL and create a database:
    ```sql
    CREATE DATABASE library_db;
    ```
   
2. Run the following SQL commands to create the necessary tables:
    ```sql
    USE library_db;

    CREATE TABLE BOOK (
        BOOK_ID INT AUTO_INCREMENT PRIMARY KEY,
        BOOK_TITLE VARCHAR(255),
        AUTHOR VARCHAR(255),
        GENRE VARCHAR(100),
        COPIES_AVAILABLE INT,
        COPIES_ISSUED INT
    );

    CREATE TABLE USERS (
        USER_ID INT AUTO_INCREMENT PRIMARY KEY,
        EMAIL VARCHAR(255) UNIQUE,
        PASSWORD VARCHAR(255)
    );
    ```
   
3. Insert sample data into the tables (optional):
    ```sql
    INSERT INTO BOOK (BOOK_TITLE, AUTHOR, GENRE, COPIES_AVAILABLE, COPIES_ISSUED) 
    VALUES
    ('The Great Gatsby', 'F. Scott Fitzgerald', 'Fiction', 10, 2),
    ('To Kill a Mockingbird', 'Harper Lee', 'Fiction', 5, 1),
    ('1984', 'George Orwell', 'Dystopian', 8, 0);
    ```

4. Run the Python code to connect to the database and interact with it.

## Requirements

- MySQL Server
- Python libraries: `pymysql`, `tkinter`, `SpeechRecognition`, `Pillow`
