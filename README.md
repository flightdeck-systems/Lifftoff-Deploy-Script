## Flightdeck Liftoff

This is just a simple and basic script that uses Bash and Rsync to deploy Flightdeck projects (or any project), that do not use NPM and the Flightdeck manifest. 



### Configuration

There are a two (2) file that need to be configured - `liftoff` and `misfits.txt` 

The `liftoff` script should be updated with your server information and path. 

The `misfits.txt` file is for excluding files and directories that should not be synced with your remote server



### Usage

There are two (2) parameters, when executing the script. 

A dry run to observe the payload that will deploy to your server. 