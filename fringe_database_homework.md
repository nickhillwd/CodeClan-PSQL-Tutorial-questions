SQL Questions

First create a database called fringe_shows

  #terminal
  psql
  create database fringe_shows;
  \q
Populate the data using the script - fringeshows.sql

  #terminal
  psql -d fringe_shows -f fringeshows.sql
Using the SQL Database file given to you as the source of data to answer the questions. Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

Section 1

Revision of concepts that we've learnt in SQL today

Select the names of all users.
SELECT name FROM users;

Rick Henri
 Jay Chetty
 Keith Douglas
 Callum Dougan
 Andrew Insley
 Daniel Gillespie
 Bethany Fraser
 Nick Ridell
 Evelyn Utterson
 Sky Su
 Nicholas Hill
 Michael McLeod
 Callum Hogg
 Chris Sloan
 Gary Carmichael
 Oscar Brooks
 Ross Galloway
 Paul MacLean
 Stuart Ramsay
 Peter Forbes
 Euan Walls
 Aine Dunphy
(22 rows)

Select the names of all shows that cost less than £15.
ringe_shows=# SELECT name FROM shows WHERE price <= '15.00';                       name
------------------------------
 Le Haggis
 Paul Dabek Mischief
 Best of Burlesque
 Two become One
 Urinetown
 Two girls, one cup of comedy
(6 rows)

Insert a user with the name "Val Gibson" into the users table.

fringe_shows=# INSERT INTO users (name) VALUES ('Val Gibson');
INSERT 0 1
fringe_shows=# select name from users;

      name
------------------
 Rick Henri
 Jay Chetty
 Keith Douglas
 Callum Dougan
 Andrew Insley
 Daniel Gillespie
 Bethany Fraser
 Nick Ridell
 Evelyn Utterson
 Sky Su
 Nicholas Hill
 Michael McLeod
 Callum Hogg
 Chris Sloan
 Gary Carmichael
 Oscar Brooks
 Ross Galloway
 Paul MacLean
 Stuart Ramsay
 Peter Forbes
 Euan Walls
 Aine Dunphy
 Val Gibson
(23 rows)

Select the id of the user with your name.
fringe_shows=# SELECT id FROM users WHERE name = 'Nicholas Hill';
 id
----
 11
(1 row)

Insert a record that Val Gibson wants to attend the show "Two girls, one cup of comedy".

fringe_shows=# SELECT id FROM users WHERE name = 'Val Gibson';
 id
----
 23
(1 row)

fringe_shows=# INSERT INTO shows_users (show_id, user_id) VALUES (12,23);
INSERT 0 1

Updates the name of the "Val Gibson" user to be "Valerie Gibson".

UPDATE users SET name = 'Valerie Gibson' WHERE name = 'Val Gibson';
UPDATE 1
fringe_shows=# SELECT * FROM users WHERE name = 'Valerie Gibson';
 id |      name
----+----------------
 23 | Valerie Gibson
(1 row)

Deletes the user with the name 'Valerie Gibson'.

DELETE FROM users WHERE name = 'Valerie Gibson'
fringe_shows-# ;
DELETE 1
fringe_shows=# select name from users
fringe_shows-# ;
       name
------------------
 Rick Henri
 Jay Chetty
 Keith Douglas
 Callum Dougan
 Andrew Insley
 Daniel Gillespie
 Bethany Fraser
 Nick Ridell
 Evelyn Utterson
 Sky Su
 Nicholas Hill
 Michael McLeod
 Callum Hogg
 Chris Sloan
 Gary Carmichael
 Oscar Brooks
 Ross Galloway
 Paul MacLean
 Stuart Ramsay
 Peter Forbes
 Euan Walls
 Aine Dunphy
(22 rows)

Deletes the shows for the user you just deleted.

fringe_shows=# DELETE FROM shows_users WHERE id = '23';
DELETE 1

Section 2

This section involves more complex queries. You will need to go and find out about aggregate funcions in SQL to answer some of the next questions.

Select the names and prices of all shows, ordered by price in ascending order.

Select the average price of all shows.

Select the price of the least expensive show.

Select the sum of the price of all shows.

Select the sum of the price of all shows whose prices is less than £20.

Select the name and price of the most expensive show.

Select the name and price of the second from cheapest show.

Select the names of all users whose names start with the letter "N".

Select the names of users whose names contain "mi".

Section 3

The following questions can be answered by using nested SQL statements but ideally you should learn about JOIN clauses to answer them.

Select the time for the Edinburgh Royal Tattoo.

Select the number of users who want to see "Shitfaced Shakespeare".

Select all of the user names and the count of shows they're going to see.

SELECT all users who are going to a show at 17:15.

Hints

As with anything, if you get stuck, move on, then go back if you have time.
Don't spend all night on it!
Use resources online to solve harder ones - there are solutions to these questions that work with what we've learnt today, but other tools exist in SQL that could make the queries 'better' or 'easier'.