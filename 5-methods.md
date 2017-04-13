# Chapter 5: Method Analysis

## Resources
The pupils resource is listed as an application route in config/routes.rb.

## Index
* In the annotations of config/routes.rb, the relevant line has the prefix "pupils" and the verb "GET".  The URL is "/pupils", and the controller action is index.
* In app/controllers/pupils_controller.rb, the relevant definition is "index".  @pupils is defined as the entire group of pupils.
* The relevant view page is app/views/pupils/index.html.erb.

## Show
* In the annotations of config/routes.rb, the relevant line has the prefix "pupil" and the verb "GET".  The URL of the first entry is "/pupils/1", and the controller action is show.
* In app/controllers/pupils_controller.rb, the relevant definition is "show".  Note that the before_action set_pupil applies for the show action.  In the set_pupil action, @pupil is defined as the pupil instance that meets the parameters specified.  Given the URL "/pupils/1", this means the pupil with the ID value of 1.
* The relevant view page is app/views/pupils/show.html.erb.

## New
* In app/views/pupils/index.html.erb, the path leading to the page for creating a new pupil is new_pupil_path.
* In the annotations of config/routes.rb, the relevant line has the prefix "new_pupil" and the verb "GET".  The URL is "/pupils/new", and the controller action is "new".
* In app/controllers/pupils_controller.rb, the relevant definition is "new".  The variable @pupil is defined as Pupil.new.
* The relevant view page is app/views/pupils/new.html.erb.  The "render 'form'" part calls the app/views/pupils/_form.html.erb page view.  Because this is a page for adding a new pupil, the submit button triggers the "create" action with the parameters entered on the page as inputs.
* In app/controllers/pupils_controller.rb, the relevant definition is "create".  The variable @pupil is defined as Pupil.new(pupil_params).  Note that pupil_params is a private method that specifies which parameters are permitted.  The create method then attempts to save this new pupil with the specified parameters.

## Edit
* In app/views/pupils/index.html.erb, the path leading to the page for editing a pupil is edit_pupil_path(pupil).
* In the annotations of config/routes.rb, the relevant line has the prefix "edit_pupil" and the verb "GET".  The URL for the first pupil is "/pupils/1/edit", and the controller action is "edit".
* In app/controllers/pupils_controller.rb, the relevant definition is "edit".  Note that the before_action set_pupil applies for the edit action.  The set_pupil method defines the variable @pupil.
* The relevant view page is app/views/pupils/edit.html.erb.  The "render 'form'" part calls the app/views/pupils/_form.html.erb page view.  Because this is a page for editing new pupil, the submit button triggers the "update" action with the parameters entered on the page as inputs.
* In app/controllers/pupils_controller.rb, the relevant definition is "update".  Note that pupil_params is a private method that specifies which parameters are permitted.  The update method then attempts to save this new pupil with the specified parameters.

## Destroy
