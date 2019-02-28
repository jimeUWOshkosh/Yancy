Mojolicious Advent Calendar 2018: Day 6: Making A List with Yancy

# Note: I don't have the internet at home so
# I put all the javascript and css stuff in a sub-directory named 'yancy'

$ sudo apt install sqlite3

$ cpanm Yancy
$ cpanm DBI
$ cpanm Mojo::SQLite

# create database
$ perl myapp.06Dec2018.pl .pl eval 'app->schema->deploy' 

$ morbo myapp.06Dec2018.pl
http://127.0.0.1:3000/yancy

