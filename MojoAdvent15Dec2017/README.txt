Mojolicious Advent Calendar 2017: Day 15: Start a New Yancy App

# Note: I don't have the internet at home so
# I put all the javascript and css stuff in a sub-directory named 'yancy'

Took me forever to get this going, so hopefully these notes are good!

$   sudo apt-get install postgresql postgresql-contrib
$   sudo apt-get install libpq-dev

# create user
$ sudo -u postgres createuser --interactive

	Output
	Enter name of role to add: dbuser
	Shall the new role be a superuser? (y/n) y

# create database
$ sudo -u postgres createdb blog

#  give user a password
$ sudo -u dbuser psql blog
ALTER USER dbuser WITH PASSWORD 'password';

$ cpanm Yancy
$ cpanm DBI
$ cpanm Mojo::PG


# login as your dbuser

# create table
$ vi stuff.sql
	CREATE TABLE blog (
	    id SERIAL PRIMARY KEY,
	    title VARCHAR NOT NULL,
	    created TIMESTAMP NOT NULL DEFAULT NOW(),
	    markdown TEXT NOT NULL,
	    html TEXT NOT NULL
	);

$ psql blog <stuff.sql

# edit progam for dbuser and password. Line 4 & 8
$ vi myapp.15Dec2017.pl


$ morbo myapp.15Dec2017.pl
http://localhost:3000/yancy

