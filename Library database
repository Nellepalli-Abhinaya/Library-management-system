-- Step 1: Create Database and Tables
CREATE DATABASE LibraryDB;
USE LibraryDB;

CREATE TABLE Books (
    BookID INT PRIMARY KEY AUTO_INCREMENT,
    Title VARCHAR(255) NOT NULL,
    Author VARCHAR(255),
    Genre VARCHAR(50),
    PublishedYear INT
);

CREATE TABLE Members (
    MemberID INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(255) NOT NULL,
    Email VARCHAR(100) UNIQUE,
    JoinDate DATE
);

CREATE TABLE BorrowedBooks (
    BorrowID INT PRIMARY KEY AUTO_INCREMENT,
    BookID INT,
    MemberID INT,
    BorrowDate DATE,
    ReturnDate DATE,
    FOREIGN KEY (BookID) REFERENCES Books(BookID),
    FOREIGN KEY (MemberID) REFERENCES Members(MemberID)
);

-- Step 2: Insert Sample Data
INSERT INTO Books (Title, Author, Genre, PublishedYear) VALUES
('The Great Gatsby', 'F. Scott Fitzgerald', 'Fiction', 1925),
('To Kill a Mockingbird', 'Harper Lee', 'Fiction', 1960),
('1984', 'George Orwell', 'Dystopian', 1949);

INSERT INTO Members (Name, Email, JoinDate) VALUES
('John Doe', 'john@example.com', '2023-01-15'),
('Alice Smith', 'alice@example.com', '2022-11-20');

INSERT INTO BorrowedBooks (BookID, MemberID, BorrowDate, ReturnDate) VALUES
(1, 1, '2024-01-10', '2024-01-25'),
(2, 2, '2024-01-12', NULL);

-- Step 3: Fetch Data Queries
SELECT * FROM Books;
SELECT * FROM Members;

SELECT bb.BorrowID, b.Title, m.Name, bb.BorrowDate, bb.ReturnDate
FROM BorrowedBooks bb
JOIN Books b ON bb.BookID = b.BookID
JOIN Members m ON bb.MemberID = m.MemberID;
