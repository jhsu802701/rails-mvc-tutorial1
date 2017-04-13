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
