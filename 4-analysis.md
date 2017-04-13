# Chapter 4: MVC Analysis

Now that you have set up the app and entered, edited, and destroyed data in it, it's time to do some more in-depth analysis.

## Model
* The file app/models/pupil.rb defines the pupil class.  If there were restrictions on the values of the pupil parameters, they would be defined here.
* The annotate gem prints a list of parameters in the comments at the beginning of the model file.

## Routes
* The Rails router (at config/routes.rb) recognizes URLs visited by the user and selects the appropriate controller action and view.  In this project, the Rails router lists pupils as a resource.
* The annotate gem prints the output of the "rails routes" command in the beginning of the config/routes.rb file.  This output includes the path name, HTTP action, path, and controller action.

## Views
The pupil view pages are in the app/views/pupils directory.  When a specific method is called by the controller, the corresponding view page is displayed.

## Controller
* The pupil controller is defined in the app/controllers/pupils_controller.rb file.
* The public methods index, show, new, edit, create, update, and destroy are defined here.  These methods are accessible to the web browser and have definitions in the config/routes.rb file.
* The private methods set_pupil and pupil_params are defined here as well.  These methods are not accessible to the web browser and do not have definitions in the config/routes.rb file.  However, the private methods are used by the public methods in the process of performing their functions.

