# Installation and Setup

Once you have extracted the files into the directory where you would like to
install Radiant:

1. Create the MySQL/PostgreSQL/SQLite/SQL Server/DB2 databases for your Web
site. You only need to create the "production" database, but you may also
want to create the "development" and "test" databases if you are developing
extensions or running tests.

2. Edit config/database.yml to taste.  There are example files available for
various databases in the config directory.

3. Run the database bootstrap rake task:
   
	% rake production db:bootstrap
   
(If you would like bootstrap your development database run `rake
development db:bootstrap`.)

If you get the error "no such file to load -- spec/rake/spectask" please
install Rspec (gem install rspec).

4. Start it like a normal Rails application. To test execute:
   
	% script/server -e production
   
And open your Web browser on port 3000 (http://localhost:3000). The
administrative interface is available at /admin/. By default the bootstrap
rake task creates a user called "admin" with a password of "radiant".

When using Radiant on a production system you may also need to set permissions
on the public and cache directories so that your Web server can access those
directories with the user that it runs under.
