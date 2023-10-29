<a name="readme-top"></a>

<!-- PROJECT LOGO -->
<br />
<div align="center">
    <h3> This is a quick tutorial for NodeMailer </h3>

- This README template was originally from <a href="https://github.com/othneildrew/Best-README-Template/tree/master">here</a>
** This is just for my own reference the full turoial is from <a href="https://www.freecodecamp.org/news/use-nodemailer-to-send-emails-from-your-node-js-server/">Freecodecamp</a>
</div>

<!-- ABOUT THE PROJECT -->

## Setup

1. Start by setting up your Express Project

```js
   pnpm init
   pnpm add express dotenv
```

2. Then create an index.js file and paste in the following code

```js
const express = require("express");
const app = express();
const port = 3000;

app.listen(port, () => {
  console.log(`nodemailerProject is listening at http://localhost:${port}`);
});
```

## NodeMailer

Nodemailer is a library API for sending emails with Node js
We can begin sending mails with these 3 requirements

1. Transporter Object : It's like where you setup your Email password token keys and stuff
2. MailOptions Object : The mail itself , from , to , subject , body
3. Transporter.sendMail : Is a method where we send the mail

First put the following code into index.js
Don't run the server yet since we still don't have the clientID , secretKey and token
We will setup those things in the next step

```js
let transporter = nodemailer.createTransport({
  service: "gmail",
  auth: {
    type: "OAuth2",
    user: process.env.MAIL_USERNAME,
    pass: process.env.MAIL_PASSWORD,
    clientId: process.env.OAUTH_CLIENTID,
    clientSecret: process.env.OAUTH_CLIENT_SECRET,
    refreshToken: process.env.OAUTH_REFRESH_TOKEN,
  },
});
```

## Setup with Google Cloud Platform
Follow the Freecodecamp instruction on this
1. Create a google cloud platform account (with Gmail is OK)

2. We will use OAuth get all the token and setup in .env file

## Sending the mail

1. Paste the mailOptions in the same file
** --- ---- is indicating a variable don't put in the ---
```js
let mailOptions = {
    from: "---ANYNAME--- <---EMAIL--->",
    to: "---EMAIL---",
    subject: 'Nodemailer Project',
    html: '<h1>Hi from your nodemailer project</h1>'
  };
```
2. Send the mail with transporter
```js
transporter.sendMail(mailOptions, function(err, data) {
    if (err) {
      console.log("Error " + err);
    } else {
      console.log("Email sent successfully");
    }
  });
```