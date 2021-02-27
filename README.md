<div align="center">
<p><img src="https://d.pr/free/i/FDUErn+" alt="Flightdeck Logo"></p>
</div>

## Flightdeck Liftoff 🚀

This is just a simple and basic script that uses Bash and Rsync to deploy Flightdeck projects (or any project)... generally Flightdeck projects are just static files so there are many other options but this is a simple just a simple solution.

### Prerequisites

We are making a few assumptions about your local and remote server.

1. You know what SSH is and that you have a key configured for your remote server.
   1. This isn't a deal breaker but you will need to enter your remote server password, if no key is available.
2. You have `rsync` installed on your local.

### Install

To install this in your project you can run the following:

```shell
wget  https://raw.githubusercontent.com/flight-deck/Flightdeck-Liftoff/master/.liftoffrc && chmod +x ./.liftoffrc
```

### Configuration

There are a couple variables that need to be configured inside of the `.liftoffrc` file

The `.liftoffrc` script should be updated with your server information and path.

- We added four (4) primary variables to make it easier to manage. - `USER`, `REMOTE`, `REMOTE_PATH`, `EXCLUDES`
- If you plan to use a multi server configuration - _ie:_ Production and Stage Servers - you will need to edit two (2) additional variables. - `REMOTE2` and `REMOTE_PATH2`

The `EXCLUDES` variable is used for excluding files and directories that should not be synced with your remote server. - see RSYNC [docs](https://download.samba.org/pub/rsync/rsync.1) for more details.

* We included a couple of defaults - `.git/` and `.DS_Store` - add more as you see fit.

### Usage

There are two (2) parameters, when executing the script.

1. `./.liftoffrc ready` - Will execute a `dry-run` to observe the payload that is ready for "liftoff" _(deploy)_ to the remote server. Think of this as a prelaunch check ✅.
2. `./liftoff ready go` - Will execute an **actual** push _(deploy)_ the payload to the remote server.
   1. Launch the payload 🛰 into orbit 🪐

