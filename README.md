# python-emailer
Simple python project to interact with Google API and send emails

# Usage
First, make sure you can successfully run the python example to get the labels: https://developers.google.com/gmail/api/quickstart/python as that example has the framework and settings for authenticating your app.

Once that is setup, these examples should work for you after making sure to update the "their_email@gmail.com" and "your_email@gmail.com". The authentication piece where you create credentials in "APIs & Services"/Credentials for your project, is where you'll be able to download the OAuth client secrets json which you will store in the same directory as your python code in "credentials.json".

I did not need any other keys or environment variables, and was able to execute the apps via commands like ```python3 send_message.py``` and it successfully sent an email to/from the email address associated with the service.

Note that when it first authenticates it will need you to accept via the browser and will print out the URL as it attempts to launch your browser. You can copy-paste that link into another browser and authenticate, but the response will not go to the app. So instead, when your browser tries to open something up at "localhost" you can finish the process with a simple ```curl -v "http://<localhost_url>"``` by copy-pasting the URL from the browser into another terminal on the device that is trying to authenticate.

# Notes
After getting the labels example to work, I was unable to get the example draft message code to work in the "Sending Email" examples due to "Precondition check failed" errors.
To resolve this, I modified the labels example to inclue the changes from the draft example and also looked up an appropriate SCOPES (gmail.compose) and it worked!
Basically to implement any of the examples that fail with the same "Precondition check failed" error, you should be able to start from these or the quickstart example and just replace the stuff in the "try" statement after:  service = build('gmail', 'v1', credentials=creds) and of course put the proper imports at the top to get going!

# References
https://console.cloud.google.com/apis/credentials/consent?project=piserveremail

