# sb_36-01-12_Message.ly_HashingAndJWTsExercise


## Technology Stack
- **Front-end**: N/A
- **Back-end**: Node.js, Express, and Postgres.


## Assignment Details

Message.ly is an Express API application that demonstrates the use bcrypt in Node.js, and the use of JSON Web Tokens (JWT) for API authentication. The base appliation code provided the structure of the API and already had modules set up for the User and Message models'; user, message, and authentication routes; and JWT middleware. The User model, messages route, auth route, and users route all required logic and only had docstrings as a guide.

**Step 1: Take a Tour** involved reviewing the base code and understanding how all the pieces fit together.. 

**Step 2: Fix the user model** 
'Fix' the user model is definitely inaccurate because `register()`, `authenticate()`, `updateLoginTimestamp()`, `all()`, `get()`, `messagesFrom()`, and `messagesTo()` methods all had to get coded using the docstrings as a guide.

**Step 3: Fix the routes** 
All of the routes specified by the docstrings in `auth.js`, `messages.js`, and `users.js` all required code. 

**Further Study** 
No further study suggestions were implemented.


## Enhancements
- Nothing major. Renamed the model files because there were too many similarly named files! The name changes were carried through in all the routes and testing files.

## Difficulties
- Lost the connection of making the `token` and getting the `token` back into the application. Just totally forgot the point that the programs that are calling the API retain the token and add the `token` to every request.
- </> RESTED would not work with this assignment. You cannot specify JSON data for the body of a GET request and finally had to break out Insomnia. 
- Error messages and too many `try` / `catch` blocks! Some messages were repeated twice in the output and with different status codes -- examples are when the user was not found. I had the db call in the method nested in a `try` / `catch` block. The user not found check which ran in the `try` block would throw the not found '404' error via `new ExpressError`. The `catch` in the method would then catch the '404' error and then `new ExpressError` with (error) , the 404, but it got imbedded in the status 500 message! FINALLY (hopefully) realized that the code within the method does not need `try` and `catch` most of the time because if anything goes wrong, the `try` and `catch` that exist where the method was called will handle the error. The only time it helped to have the `try` / `catch` in the db method is to catch a specific error code.
