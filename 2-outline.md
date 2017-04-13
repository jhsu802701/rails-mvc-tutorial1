# Chapter 2: Outlining the App

## Updating the Gemfile
* Add the following lines to the end of the Gemfile:
```
# BEGIN: for outline.sh
group :development do
  gem 'annotate' # Adds comments listing parameters and the output of "rails routes"
  gem 'railroady' # Generates block diagrams
  gem 'rails-erd' # Generates block diagrams
end
# END: for outline.sh
```
* Enter the command "bundle install".  This action installs the annotate, railroady, and rails-erd gems.

## outline.sh
* Create the file outline.sh in your app's root directory, and give it the following content:
```
echo '-----------------------------'
echo 'bundle exec annotate --routes'
bundle exec annotate --routes

echo '--------------------'
echo 'bundle exec annotate'
bundle exec annotate

d_mo='log/diagram-models.jpg'
d_co='log/diagram-controllers.jpg'

echo '---------------'
echo 'Using rails-erd'
bundle exec erd --attributes=foreign_keys,primary_keys,timestamps,inheritance,content --filetype=dot --filename=log/diagram-models --inheritance --notation=bachman
dot -Tjpg log/diagram-models.dot > $d_mo
echo
echo "Models diagram is at $d_mo"
echo

echo '---------------'
echo 'Using railroady'
bundle exec railroady -i -l TestLabel -v -a --all-columns -j -m -p -z -t --engine-controllers -C | dot -Tjpg > $d_co
echo
echo "Controllers diagram is at $d_co"
echo

echo '************************'
echo 'outline.sh OUTPUT FILES:'
echo $d_mo
echo $d_co
```
* Enter the command "sh outline.sh" to make use of the annotate, rails-erd, and railroady gems.
* The annotate gem automatically adds comments to key files.  The output of the "rails routes" command is automatically added as comments to the config/routes.rb file.
* The rails-erd gem automatically creates a block diagram of the models in your app.  Because this app has no models yet, there is no block diagram to view yet.
* The railroady gem automatically creates a block diagram of the controllers in your app.  So far, the only controller in this app is the basic application controller.

## Conclusions
* You can now automatically outline your app.  However, there is very little to outline at this point.
* The annotate, rails-erd, and railroady gems are indispensable for large and complex apps.  Trying to read all of the code in such an app makes my head spin.
