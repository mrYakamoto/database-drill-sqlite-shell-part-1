# Database Drill Sqlite Shell Part 1 
 
##Learning Competencies 

* Use SQLite and the SQLite console to query data
* Use common SQL Queries to view specific data

##Summary 

Let's jump into more complex SQL with a relatively large database of students.  [Download the 'students.db' file](https://github.com/downloads/dbc-challenges/binary_store/DB02_SQL_students.db).

Load up the DB file into sqlite3 - `sqlite3 students.db`.  You should now be in SQLite shell.

Orient yourself by typing `.schema`.  Notice all the columns that are available to query!  See if there are other database tables by typing `.tables`.  See all the database files open by typing `.databases`.

##Releases

###Release 0 : Select and Trace

Go ahead and make a giant list of all the students using a `SELECT` statement.  Show all the columns.

Since we are just learning, let's turn on "tracing" so we'll have a file of all the queries we're doing for this challenge.  Type `.trace sql_history.txt`.  Now all the commands will be saved!

**NOTE**: '.trace' only works with the latest version of sqlite3.  If you are having problems running it on a DBC machine, quit out of the sqlite3 console and type `brew link sqlite3` from the command line. Then, start a new Terminal session (close the window and open a new one) and you should be running with the latest version.


Which student has the ID 13?  Ooooooo, that's unlucky.  Who has the ID 77?  Remember the `WHERE` function?

###Release 1 : Where, Count, and Exporting

Create a list of all the male students.  How about the female students?  How many men are there?  How many women?  Use the `COUNT` function.

Let's put the list of all the female students in a file.  Type `.output female_students.txt`.  Now do the query for the female students.  The list shouldn't be shown on your terminal, but it should now be saved in the file.

Type `.quit` and then `subl female_students.txt`.  You should see the big file of all the female students!  Make sure your `sql_history` file is there by typing `ls`.

Then start up the database again `sqlite3 students.db`.  Let's change the output back to the terminal or STDOUT.  Type `.output stdout`.

###Release 2 : The LIKE method

Let's play around with SQLite's `LIKE` method.  It works similar to regular expressions, but with it's own syntax.  See if you can figure out the below calls:

Create a list of all the people with .com email addresses.  List only their names and their email addresses.  How many .com email addresses are there?  How many .info?

Find all the people that have a phone number with an extension.  (Look at the whole list to make sure you are matching the different variations of an extension - ie `x3467` or `x29987`)  Create an alphabetical list of all the people with an extension on their phone number AND have a ".com" email address.

###Release 3 : Group and Count

Create a count of the male and female students.  Use the `GROUP` method to create a nice clean output that shows just the gender name and count.  Like this:

```
gender      COUNT(gender)
----------  -------------
female      462
male        516
```

This is trickier... You may have to search up the answer or ask your fellow boots!

###Release 4 : Ordering and Limiting

Order everyone by birthdate in ascending order.  Order alphabetically by last name.  Now first name?  Now list only the first and last names and their birthday.  And then order those names by birthdate in descending order!

Then list just the oldest 10 students.  Now list the youngest 10 students.

Is the SQL coming back to you?  Find a cheat sheet for reference if you need to!

Quit out of sqlite, do `subl sql_history.txt`, and paste the history of all your SQL commands into the source file `sqllite_shell_1.md`.  Add comments to organize these commands. 
 

##Optimize Your Learning 

##Resources