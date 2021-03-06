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
* The log/diagram-models.jpg file now shows the pupil model and its parameters in the block diagram.
* The log/diagram-controllers.jpg file now shows the pupil controller and its methods in the block diagram.

## Viewing the App and Database
* In your web browser, add "/pupils" to the end of the URL, and press Enter.  You should now see the index of pupils, which is currently empty.
* Click on "New Pupil".  Enter the name "Clement Lefebvre" and the form "Clem".  Click on "Back" when you are finished to return to the pupil index.  Now the index shows the pupil you just entered.
* Click on "New Pupil".  Enter the name "Vincent Vermeulen" and the form "Xenopeek".  Click on "Back" when you are finished to return to the pupil index.  Now the index shows both of the pupils you just entered.
* Click on "New Pupil".  Enter the name "Suzanne" and the form "Oscar799".  Click on "Back" when you are finished to return to the pupil index.  Now the index shows all of the pupils you just entered.
* Use the SQLite Browser in your host OS to view the database again.  Go to the pupils table and press the refresh button.  The pupils table should now include the pupils you entered.
* Click on "New Pupil".  Enter the name "Homer Simpson" and the form "bartender".  Click on "Back" when you are finished to return to the pupil index.  Now the index shows all of the pupils you just entered.
* Use the SQLite Browser in your host OS to view the database again.  Go to the pupils table and press the refresh button.  Homer Simpson should be on the list.
* In the row containing "Homer Simpson", click on "Edit".  Change the form parameter to "power plant operator".  Click on "Update Pupil".  Now you'll see that the form parameter is updated.  Click on "Back" to return to the pupil index.  Now you'll see Homer Simpson listed as a power plant operator.
* Use the SQLite Browser in your host OS to view the database again.  Go to the pupils table and press the refresh button.  Homer Simpson should be in the table and listed as a power plant operator.
* In the row containing "Homer Simpson", click on "Destroy".  When you are asked, "Are you sure?", click "OK" in the dialog box.  You'll see that Homer Simpson no longer shows up in the pupil index.
* Use the SQLite Browser in your host OS to view the database again.  Go to the pupils table and press the refresh button.  The Homer Simpson entry should be gone.

