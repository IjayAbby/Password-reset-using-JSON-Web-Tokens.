# Password-reset-using-JSON-Web-Tokens.
Creating a secure password resets using JSON Web Tokens.
# Resetting The User’s Password.

The application will display a form that accepts the user’s email address.
It will handle the form’s POST with the user’s email address.
This will create a link, with a JWT token embedded in the URL. The user will click this link and be allowed to reset their password.
The application will create a password-reset page. This page will require the token and will decode it to ensure it is valid.
If successful, a form will be displayed allowing the user to reset their password.
The application will handle the form’s POST with the user’s new password.
This page will also decode and validate the token before saving the new password.

Additional Password-Reset Security Measures
Our application focuses specifically on securing the password-reset form by generating and validating a special link embedded
with a JWT.
This is just the tip of the iceberg to ensure that the entire password process is more secure. 
Below is a list of several other enhancements that could further secure your website:

Limit the number of password-reset attempts to prevent a malicious user from giving your end user a negative experience of 
flooding their inbox with password-reset emails.
Always indicate success when the user enters their email address in the forgotten-password page.
Ensure that your website uses HTTPS to prevent any plain-text communication between the user and server when they are 
entering or resetting their password.
Ensure that the user’s new password is secure and is not the same as their last password.
Implement a CAPTCHA — the “Are you a human?” test — on both the forgotten-password and password-reset pages. 
Some websites even implement the CAPTCHA test on the log-in screen.
Implement forgotten-password security questions, where the user must answer a security question (that they’ve previously created) before an email is ever sent to reset their password.


“How Else Can I Use JWTs?”
By now, I’ll bet you are addicted to creating and consuming JWTs! Now you want to use them more. 
Here are a few examples of how else I have used them:

Single sign-on
A friendly third-party website would generate a JWT with information that your website would require to authenticate the user in your application. You and the friendly website would privately share the secret key used to encode and decode the token.
Information exchange
Similar to single sign-on, you or the friendly website would generate a token with a privately shared secret key that 
contains the information you wish to send or receive. Be sure not to share sensitive data!
Tokens required for the “OAuth dance”
Note that, because a generated JWT is a string, it can be decoded by a server other than the one that generated it. 
For example, you might generate a token with your Node.js server, and I could consume it with my PHP application as 
long as we use the same secret key and hashing algorithm!
