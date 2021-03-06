# Drupal Build Script

This is a small shell script to easily automate a Drupal site build primarily using [Drush][].
Site deployment, public key transfer etc. is planned for later.


## What it actually does
### -m | make
1.  Uses Drush Make to download all desired modules and translations
2.  Uses Drush to install Drupal with your uid1 of choice
3.  Creates a database on localhost (As this is localhost root is passwordless, 
    change if necessary).
4.  Opens the browser with a one-time change password link to your local site.

### -d | deploy
1.  Creates a drush alias file for dev and live servers
2.  Sends your public key over ssh to the remote host
3.  <del>Install drush on remote host</del>
4.  <del>Create a database and a user on remote host</del>
5.  <del>Transfer the Drupal directory as well as the database</del>

### -s | sync
1.  <del>Use drush rsync functionality to sync directories and database</del>


## Setup
1.  Install [Drush][] and [Drush Make]
2.  Setup Drush Make to your liking
2.  Create a drushrc.php file with an alias location variable
3.  Configure the bash script to your liking, if you want your downloaded modules
    to be installed add them in the $MODULES\_x variables. Some basic info about the 
    dev box is required.
4.  Add this folder to your $PATH variable
5.  drupal -m

[Drush]: http://www.drush.ws
[Drush Make]: http://drupal.org/project/drush_make

