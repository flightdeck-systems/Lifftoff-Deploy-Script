<div align="center">
<p><img src="https://rdm.sfo2.digitaloceanspaces.com/flightdeck/v3-flightdeck__logo--purple-haze-600x528.png" alt="Flightdeck Logo"></p>

[![release](https://img.shields.io/github/release/flight-deck/flightdeck-liftoff.svg?style=for-the-badge&logo=github&logoColor=white&colorA=101119&colorB=6D57FF)](https://github.com/flight-deck/flightdeck-liftoff/releases/latest)

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
wget  https://raw.githubusercontent.com/flight-deck/Flightdeck-Liftoff/master/.liftoffrc && chmod +x .liftoffrc
```

**☝️ What this does**

So the above command uses `wget` to download, just the `.liftoffrc` file into the current working directory.

From there we run `chmod +x` on the downloaded `.liftoffrc` file to make it executable for the shell.

### Configuration

There are a few variables that need to be configured inside of the `.liftoffrc` file before you can use it.

You will need to configure your server information and your destination path.

- We added four (4) primary variables to make it easier to manage. - `$USER`, `$REMOTE`, `$REMOTE_PATH`, `$EXCLUDE`
- If you plan to use a multi server configuration - _ie:_ Production and Stage Servers - you will need to edit two (2) additional variables. - `$REMOTE2` and `$REMOTE_PATH2`

The `$EXCLUDE` variable is used for excluding files and directories that you do not want to be included in the deployment to your remote server. - see RSYNC [docs](https://download.samba.org/pub/rsync/rsync.1) for more details, if you are curious about it.

An example:

```bash
EXCLUDE=(
   'node_modules/'
   'package-lock.json'
   'yarn.lock'
   '.liftoffrc'
)
```

### Usage

There are two (2) parameters, to execute the script.

1. `./.liftoffrc ready` - Will execute a `dry-run` to observe the payload that is ready for "liftoff" _(deploy)_ to the remote server. Think of this as a prelaunch check ✅.
2. `./liftoffrc ready go` - Will execute an **actual** push _(deploy)_ of the payload to the remote server.
   1. Launch the payload 🛰 into orbit 🪐

### Use with NPM or Yarn

There is no NPM package to install for Liftoff 🚀 but you can take advantage of NPM scripts inside of your `package.json`

Add the following to your `package.json`

```json
"scripts": {
   "deploy:test": "./.liftoffrc ready",
   "deploy:live": "./.liftoffrc ready go",
}
```

Now you can run

`npm run deploy:test` OR `npm run deploy:live`

or

`yarn deploy:test` OR `yarn deploy:live`
