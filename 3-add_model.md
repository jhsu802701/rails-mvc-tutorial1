# Chapter 3: Adding the Model

## Creating and Outlining the Model
* Enter the command "rails g scaffold Pupil name:string form:string".  This generates the pupil model with the string parameters name and form.  The scaffold creates controllers and pages to view, create, and delete pupils.
* Enter the command "rails db:migrate".
* Enter the command "sh outline.sh".

## Viewing the App
* In your web browser, add "/pupils" to the end of the URL, and press Enter.  You should now see the index of pupils, which is currently empty.
