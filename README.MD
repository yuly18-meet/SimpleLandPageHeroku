SO KIDS!


! you clone this repo

! next you cd into this project folder

! run commands:

git init
git add .
git commit -m "first commit"
heroku create YOUR_APP_NAME_INSTEAD_OF_BLOCK_CAPITALS
git push heroku master

! then you run the following

heroku addons:add heroku-postgresql:hobby-dev

! This sets up a heroku hobby developer postgres db on you heroku account

! look: once it has provisioned a database you should get the following code:

heroku addons:add heroku-postgresql:hobby-dev

Creating heroku-postgresql:hobby-dev on ⬢ flaskpos... free
Database has been created and is available
 ! This database is empty. If upgrading, you can transfer
 ! data from another database with pg:copy
Created postgresql-fluffy-53405 as HEROKU_POSTGRESQL_ORANGE_URL

! THIS IS WHAT YOU ARE AFTER: HEROKU_POSTGRESQL_ORANGE_URL (name of your db in heroku)

! next run  run the following command with the DB color tag Heroku gave you:

heroku pg:promote HEROKU_POSTGRESQL_ORANGE_URL

! This links the db URL of the hobby dev created to your app that you deployed

! next are these commands:

heroku run python
>>> from app import db
>>> db.create_all()
>>> exit()

and BOOM!
you got a landing page.


! to query the db run:

heroku pg:psql

and then when pg opens you can do as we learned in class:

SELECT * FROM users;

etc........

GOOD LUCK!




