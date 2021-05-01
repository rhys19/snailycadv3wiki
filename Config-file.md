**Below you can see what all the config items are**

- `port`: This is the port of where you want to host the CAD. Not of your database.
- `host`: Where your database is hosted. For most users, keep this as is.
- `user`: The user that you want to use to connect to the MySQL database
- `password`: The password of the above user
- `databaseName`: The name of the created database for snaily-cad. For most users, keep this as is.
- `jwtSecret`: A random string and numbers, letters and random characters
- `env`: The environment. Either `production` or `dev`. For most users, keep this to `production`
- `allowIframes`: allow iframes. **Your domain requires to have `https://`!**
- `secureCookies`: if the cookies should be secure. **Your domain requires to have `https://`!**