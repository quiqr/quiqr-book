---
title: Pogoforms Quickstart
weight: 10
---

# Pogoform Quickstart

To quickly understand how Pogoforms works, try to implement the example form
configuration below in your PoppyGo website. After implementing the form, you
need to publish your website to the PoppyGo Cloud.

## Example form configuration

Below is a minimal form html to use in your Hugo Layout. You need to put
`POGOFORM` in the form action to use the pogoform-service.

```html
<form method="post" action="POGOFORM">
  Name: <input type="text" name="name" /><br/>
  Email: <input type="text" name="email" /><br/>
  <textarea name="message" placeholder="Message"></textarea><br/>
  <input type="submit" value="send" />
  <input type="hidden" name="POGOFORM_ID" value="default">
</form>
```

Here's a configuration belonging to above form in the file
`poppygo/forms/default.yml`

```yaml
---
subject: Website contact form
to: info@example.com
redirect_to: /contact/thanks/
senders_email_field: email
reply_to_sender: true
antispam: slide
validations:
  fields:
    email:
      type: email
      empty: false
      mandatory: true
    name:
      type: string
      empty: false
      mandatory: true
    message:
      type: string
      empty: false
      mandatory: true
```
