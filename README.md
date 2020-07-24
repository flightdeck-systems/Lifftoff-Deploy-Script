## Flightdeck Liftoff

This is just a simple and basic script that uses Bash and Rsync to deploy Flightdeck projects (or any project), that do not use NPM and the Flightdeck manifest.

### Prerequisites

We are making a few assumptions about your local and your remote server.

1. You know what SSH is and that you have key on the remote server. - this isn't a deal breaker but you will need to enter your password if no key is available.
2. You have `rsync` installed on your local.


### Configuration

There are a two (2) file that need to be configured - `liftoff` and `misfits.txt`

The `liftoff` script should be updated with your server information and path.

The `misfits.txt` file is for excluding files and directories that should not be synced with your remote server



### Usage

There are two (2) parameters, when executing the script.

A dry run to observe the payload that will deploy to your server.
