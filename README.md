# SequentialAuthServer

The project targets to add tokens to every api call and validate the previous token.

The approach is to check if the calls between server and client are getting tampered.

## Tech stack

1. Japronto (uses uvloop, runs on linux, fork server)
2. uuid.uuid1() which considers the current time to generate unique UUID

## Usage

1. Run the server
2. The client first needs to login and get a token
3. Use the token to make an api call and get another token after the call (which will be used for next call)

Note: Previous token will be invalidated. Using invalid token will result the server to respond with HTTP 401 error code

