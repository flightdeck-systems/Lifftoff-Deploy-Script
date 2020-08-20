## Flightdeck Liftoff 🚀

This is just a simple and basic script that uses Bash and Rsync to deploy Flightdeck projects (or any project), that do not use NPM and the Flightdeck manifest.

### Prerequisites

We are making a few assumptions about your local and your remote server.

1. You know what SSH is and that you have a key configured for your remote server.
   1. This isn't a deal breaker but you will need to enter your remote server password, if no key is available.
2. You have `rsync` installed on your local.


### Configuration

There are a two (2) files that need to be configured - `liftoff` and `.liftoffrc`

The `liftoff` script should be updated with your server information and path.

- We added three (3) primary variables to make it easier to manage. - `USER`, `REMOTE`, `REMOTE_PATH`
- If you plan to use a multi server configuration - _ie:_ Production and Stage Servers - you will need to edit two (2) additional variables. - `REMOTE2` and `REMOTE_PATH2`

The `.liftoffrc` file is used for excluding files and directories that should not be synced with your remote server.

* We included a couple of defaults - `.git/` and `.DS_Store`

### Usage

There are two (2) parameters, when executing the script.

1. `./liftoff ready` - Will execute a `dry-run` to observe the payload that is ready for "liftoff" _(deploy)_ to the remote server. Think of this as a prelaunch check ✅.
2. `./liftoff read go` - Will execute an **actual** push _(deploy)_ the payload to the remote server.
   1. Launch the payload 🛰 into orbit 🪐

