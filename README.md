# goit-rdb-hw-04

1)
 CREATE SCHEMA LibraryManagement;

 CREATE TABLE authors (
	 author_id INT AUTO_INCREMENT PRIMARY KEY,
  author_name VARCHAR(45)
);

CREATE TABLE genres (
	 genre_id INT AUTO_INCREMENT PRIMARY KEY,
  genre_name VARCHAR(45)
);

CREATE TABLE books (
	book_id INT AUTO_INCREMENT PRIMARY KEY,
 title VARCHAR(45),
 publication_year YEAR,
 author_id INT, FOREIGN KEY (author_id) REFERENCES authors(author_id),
	genre_id INT, FOREIGN KEY (genre_id) REFERENCES genres(genre_id)
);

CREATE TABLE users (
	user_id INT AUTO_INCREMENT PRIMARY KEY,
 username VARCHAR(45),
 email VARCHAR(45)
);

CREATE TABLE borrowed_books (
	borrow_id  INT AUTO_INCREMENT PRIMARY KEY,
 book_id INT, FOREIGN KEY (book_id) REFERENCES books(book_id),
	user_id INT, FOREIGN KEY (user_id) REFERENCES users(user_id),
	borrow_date DATE,
	return_date DATE
);

2)
INSERT INTO authors (author_id, author_name)
VALUES 
	(1, 'George Orwell'),
    	(2, 'Jane Austen'),
    	(3, 'Harper Lee');
    
INSERT INTO genres (genre_id, genre_name)
VALUES 
	(1, 'Dystopian Fiction'),
    	(2, 'Romance'),
    	(3, 'Fantasy');
    
INSERT INTO users (user_id, username, email)
VALUES 
	(101, 'John Doe',	'john@example.com'),
	(102,	'Jane Smith',	'jane@example.com'),
	(103,	'Bob Lee',	'bob@example.com');    
    
INSERT INTO books (book_id, title, publication_year, author_id, genre_id)
VALUES 
	(1,	'1984',	1949, 1, 1),
    	(2, 'To Kill a Mockingbird', 1960, 2, 2),
    	(3, 'Harry Potter and the Sorcerer''s Stone', 1997, 3, 3);
    
INSERT INTO borrowed_books (borrow_id, book_id, user_id, borrow_date, return_date)
VALUES 
	(1,	1,	101, '2025-02-01', '2025-02-15'),
	(2,	2,	102, '2025-02-05', '2025-02-19');
