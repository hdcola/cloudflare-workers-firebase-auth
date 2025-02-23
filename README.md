# cloudflare-workers-firebase-auth

**Zero-dependencies** firebase auth library for Cloudflare Workers.


## Run example code

1. Clone this repository
2. Install dev dependencies as `pnpm` command.
3. Global install `firebase-tools` as 
```shell
npm install -g firebase-tools
```
4. Run firebase auth emulator as 
```shell
pnpm start-firebase-emulator
```
5. Access to Emulator UI in your favorite browser.
6. Create a new user on Emulator UI. (email: `test@example.com` password: `test1234`)
7. Run example code on local (may serve as `localhost:8787`) by 
```shell
$ pnpm start-example
```
8. Get jwt for created user by
```shell
curl -s http://localhost:8787/get-jwt | jq .idToken -r
```
1.  Try authorization with user jwt 
```shell
curl -X POST http://localhost:8787/verify-header -H 'Authorization: Bearer PASTE-JWT-HERE'
```

### for Session Cookie

You can try session cookie with your browser.

Access to `/admin/login` after started up Emulator and created an account (email: `test@example.com` password: `test1234`).