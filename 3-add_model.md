# Chapter 3: Adding the Model

## Creating the Model
Enter the command "rails g scaffold Pupil name:string form:string".  This generates the pupil model with the string parameters name and form.  In addition, this action adds a database migration script, a pupils route, a pupil controller containing pupil methods, a pupil helper, web pages for pupil methods, and stylesheets for the pupil web pages.

## Database Migration
* Enter the command "rails db:migrate".  This runs the database migration, which means running the scripts in the db/migrate directory.  This directory now contains a script for creating the pupils in the database.
* The db/schema.rb script is now updated to include the process of adding the table "pupils" with the parameters "name", "form", "created_at", and "updated_at".
* Use the SQLite Browser in your host OS to view the database again.  Now the tables schema_migrations and pupils are added.  The pupils table includes the expected parameters, but there are no entries in this table yet.

## Outlining
* Enter the command "sh outline.sh".  
* The config/routes.rb file now shows the URLs relating to the pupils methods.
* The app/models/pupil.rb file now contains a list of the pupil parameters in comments at the top of the file.
* The app/controllers/pupils_controller.rb file now has the routes provided in comments just before each of the corresponding method definitions.

## Viewing the App
* In your web browser, add "/pupils" to the end of the URL, and press Enter.  You should now see the index of pupils, which is currently empty.
* Click on "New Pupil".  Enter the name "Clement Lefebvre" and the form "Clem".  Click on "Back" when you are finished to return to the pupil index.  Now the index shows the pupil you just entered.
* Click on "New Pupil".  Enter the name "Vincent Vermeulen" and the form "Xenopeek".  Click on "Back" when you are finished to return to the pupil index.  Now the index shows both of the pupils you just entered.
* Click on "New Pupil".  Enter the name "Suzanne" and the form "Oscar799".  Click on "Back" when you are finished to return to the pupil index.  Now the index shows all of the pupils you just entered.

## Viewing the Database
Use the SQLite Browser in your host OS to view the database again.  Go to the pupils table and press the refresh button.  The pupils table should now include the pupils you entered.
