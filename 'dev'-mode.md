**⚠⚠ For developers only! ⚠⚠**

## How to enable 'dev' mode

### Server
1. Create a `.env` file in the `server` folder
2. Add the following to the file:
    - `CLIENT_URL`: the URL where the client is hosted, EG `CLIENT_URL="http://localhost:3000"`
    - `IS_DEV`: boolean EG: `IS_DEV=true`

### Client

1. Create a `.env` file in the `client` folder
2. Add the following to the file:
   - `REACT_APP_SERVER_URL`: the URL where the server is hosted, EG `REACT_APP_SERVER_URL="http://localhost:3030"`
   - `REACT_APP_IS_DEV`: boolean EG: `REACT_APP_IS_DEV=true` 