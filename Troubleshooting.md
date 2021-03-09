

**This wiki page is for finding answers to common issues when installing or starting the CAD/MDT**

- [I get an error saying that `ts-node is not found/not a command`](#i-get-an-error-saying-that-ts-node-is-not-foundnot-a-command)
- [I get an error saying `cannot find module dotenv/config`](#i-get-an-error-saying-cannot-find-module-dotenvconfig)
- [I try to run `/callxxx` but it won't show up in the CAD/MDT](#i-try-to-run-callxxx-but-it-wont-show-up-in-the-cadmdt)
- [I followed the steps for updating the CAD, but still says it's outdated!](#i-followed-the-steps-for-updating-the-cad-but-still-says-its-outdated)
- [I correctly installed the live_map resource, but I don't see anyone on the livemap!](#i-followed-the-steps-for-updating-the-cad-but-still-says-its-outdated)


### I get an error saying that `ts-node is not found/not a command`

  - run `npm install -g ts-node`

### I get an error saying `cannot find module dotenv/config`

  - run `cd server && npm install dotenv`

### I try to run `/callxxx` but it won't show up in the CAD/MDT

  - Make sure that you've configured the config in `server.lua` in the download

### I followed the steps for updating the CAD, but still says it's outdated!
  - 1: Run: `git stash` in the root folder of the CAD/MDT
  - 2: Follow the rest of the update steps
  - 3: Should be updated

### I correctly installed the live_map resource, but I don't see anyone on the livemap!

  - 1: Make sure to have put in your Steam api key in the CAD-settings [Get it here](steamcommunity.com/dev/apikey)
  - 2: Once you've added the Steam api key, all Officers, EMS and FD will need to authenticate with Steam in the accounts page
  - 3: Done! Now you should see them on the live map