
- [Requirements](#requirements)
- [Video Guides](#video-guides)
- [Written Guides](#written-guides)
  - [Installing SnailyCAD](#installing-snailycad)
  - [Updating SnailyCAD](#updating-snailycad)

## Requirements

**Please make sure to have all of these installed!**

- [GIT](https://git-scm.com/downloads)
- [NodeJS v14](https://nodejs.org) (**Must be v14 or you'll run into problems!**)
- [MySQL](https://www.apachefriends.org/download.html)

## Video guides

- [Quick Installation guide](https://youtu.be/dO8qXSDDUag)
- [How to update the CAD](https://youtu.be/RV6KeeN4AA4)

## Written guides

### Installing SnailyCAD

1. Open Command Prompt
2. Run `git clone https://github.com/Dev-CasperTheGhost/snaily-cadv3`
3. Run `cd snaily-cadv3`
4. Run `npm run auto-install` and wait it to finish
5. Open the `server` folder
6. Make a copy of `config.example.ts` and rename to `config.ts`
7. Modify that where needed
8. Go back to your command prompt
9. Once done modifying, create a new database in XAMPP phpmyadmin, call it `snaily-cad` or whatever you called it in the config file
10. Import `snaily-cad.sql` into that database
11. Go back to your command prompt and make sure you are in the main folder (snaily-cadv3/)
12. Run `npm start`, this will start both client and server
13. Wait a few seconds until it logs "CAD IS RUNNING ON \<port\>"
14. The CAD should be running on <http://localhost:3030> by default

### Updating SnailyCAD

1. Run `git pull origin main` in the root folder of the CAD/MDT
   - I get an error saying `Please commit or stash your changes`, please checkout the [troubleshooting guide](https://github.com/Dev-CasperTheGhost/snaily-cadv3/wiki/Troubleshooting)
2. Run `npm run auto-install` also in the root folder of the CAD/MDT
3. Once that's finished you can start the CAD/MDT and all should be updated
