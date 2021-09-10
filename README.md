# SDSA Helpdesk

This repo contains all the files and information necessary for running Seattle DSA's Helpdesk.
We use [Zammad](https://zammad.org/) as our open source ticketing system, and [Caddy](https://caddyserver.com/) to manage HTTPS.

## Deployment

The application can be deployed with `docker-compose up -d` and taken down with `docker-compose down`.
All persistent data is stored in Docker volumes and will be retained across restarts.

## Email

We're using [Private Email](privateemail.com) for our system emailing.
The configuration is as follows:

- Server: `mail.privateemail.com`
- Username: `help@seattledsa.org`
- Password: You wish ;)
- Port: 465 for SMTP, 993 for IMAP

Zammad can be really weird about setting up the email configurations.
Just go for it with the info we have above (if it needs to be reconfigured) and everything should work out.
If the email address ever changes, you'll need to change the "Notification Sender" in the Email settings to match that, otherwise Private Email will reject the authentication.

## WordPress integration

The "Form" section of the settings pane has all the information needed for adding a modal form to our WordPress site.
The form modal does not require a user to be logged in, and all communication can happen over email.
The provided HTML can be added in an HTML block within WordPress.
JQuery **is** required, so be sure to add that too!

Also, the provided `button` tag can be changed to an anchor tag with `class="button"`.
This will make the form button look like all of the other buttons on the site.