# Chapter 1: Starting the New App

## New Rails App
* Create the new Rails app by entering the command "rails new mvc1".
* Enter the command "cd mvc1" to enter your new app's root directory.

## Database
* Enter the command "rails db:migrate", which migrates the database.  This action creates the db/schema.rb and development.sqlite3 files.
* The db/schema.rb is automatically generated every time you perform the database migration.
* Use the SQLite Browser on your host system to view the current state of the database in the development.sqlite3 file.
* At this early stage, there is nothing of significance in the db/schema.rb script or development.sqlite3 database.

## server.sh
* Create the server.sh file with the following content:
```
#!/bin/bash

echo 'View page at http://localhost:3000/'
echo 'If you are using Docker or Vagrant,'
echo 'the port number may be something else.'
echo 'If you are using Docker Machine,'
echo 'replace "localhost" with a numerical' 
echo 'IP address (probably 192.168.99.100).'

echo '-----------------------'
echo 'rails server -b 0.0.0.0'
rails server -b 0.0.0.0
```
* In Docker, enter the command "tmux" to begin tmux mode. Press Ctrl-b and then "c" to create a second tmux window. In one of your tmux screens, cd into your project's root directory, and enter the command "sh server.sh" to run your local server. Use a browser in the host machine to see what your Rails app looks like. Use the other tmux screen to continue entering commands. Press Ctrl-b and then "p" to go to the previous tmux screen. Press Ctrl-b and then "n" to go to the next tmux screen. To scroll within a tmux screen, press Ctrl-b and then your normal keys for paging up and paging down. To exit scroll mode (which disables your ability to do anything other than scroll up or down), press Ctrl-c. If you need to stop the server for any reason, just go to that tmux screen and press CTRL-c. To close a tmux screen, go to that screen and enter "exit".
* I recommend always keeping a tmux window dedicated to the local server, because it shows you what a visitor to your site would see. You should always keep the local server running when you are working on your project. There may be times when you need to shut down and then restart the local server.
* From your host system, open the ports.txt file within the shared directory of the Docker container. (Alternatively, you can enter the command "cat /home/winner/shared/ports.txt" from your Docker container.) Note the host port that corresponds to port 3000 in Docker. That's the port number to enter in your web browser in order to view the app.
* While the local server is running, open the web browser in your host environment and go to the appropriate URL. You should see the Ruby on Rails default splash screen. Keep this web browser tab open, and refresh it periodically to see the progress in this project.

## Conclusion
Congratulations!  You have now created a blank Rails app.
