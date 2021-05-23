# Testing Email

To test email, we can run a fake SMTP server. The configuration for emails can be sent set through environment variables, and we can also query back the emails to validate the content in tests.

For nodejs:
- https://www.npmjs.com/package/maildev
- https://www.npmjs.com/package/mailhog (provides api)

For golang:
- https://github.com/emersion/go-smtp
- https://www.mailslurper.com/

Alternative is to just log to stdout/or string buffer, and just validate the result.
