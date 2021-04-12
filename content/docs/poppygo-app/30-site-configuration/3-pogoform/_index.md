---
title: HTML Forms endpoint
---

# HTML Forms endpoint

Sites which are published to PoppyGo Cloud can use the `pogoform.com` service
for sending e-mails. The configuration of the form-endpoint is done with a yaml-file.

## Pogoform.com Configuration

The form configuration is located in the folder `poppygo/forms/`. You need a
least `poppygo/forms/default.yml`

### Forms properties

| property                             | value type     | optional                  | description                                                                                                                 |
|--------------------------------------|----------------|---------------------------|-----------------------------------------------------------------------------------------------------------------------------|
| subject                              | string         | mandatory                 | value is used as subject for the email                                                                                      |
| to                                   | string         | mandatory                 | e-mail address which will receive the form                                                                                  |
| redirect_to                          | string         | mandatory                 | relative link to redirect after the form as been sent                                                                       |
| antispam                             | string (slide) | optional                  | Currently the antispam method is `slide`. Before sending the form the user must prove to be human be pulling a slider       |
| timezone                             | string         | optional (default: null)  | Time zone to use for time logging. e.g. America/Havana                                                                      |
| senders_email_field                  | string         | optional (default: null)  | Pointer to the form field containing the visiters email address                                                             |
| reply_to_sender                      | boolean        | optional (default: false) | If senders_email_field is set and reply_to_sender is set true, the `Reply-To` header is set to value of senders_email_field |
| origin_allow                         | string         | optional (default: null)  | When set to a domain only email are sent when the referer is the same as this value                                         |
| validations                          | array          | optional (default: null)  | array with validation configurations. See Validation properties                                                             |
| validations.fields.[form_field_name] | dictionary     | optional                  | the dictionary depends on the field type                                                                                    |

### Validation field properties

| property  | value type               | optional  | description                                                                              |
|-----------|--------------------------|-----------|------------------------------------------------------------------------------------------|
| type      | string (string, email)   | mandatory | Depending on type the field get validated                                                |
| mandatory | boolean (default: false) | optional  | If set true the field must be part of the POST data                                      |
| empty     | boolean (default: null)  | optional  | If set true the field value must be empty, if set false to field value must be not empty |

### HTML form special properties

| element + attribute | value type | optional                    | description                                                                                                                                                                                                                                 |
|---------------------|------------|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \<form\> action     | string     | mandatory                   | This value needs to be set to `POGOFORM` in capitals                                                                                                                                                                                        |
| \<hidden\> name     | string     | optional (default: default) | To use an alternative pogoform.com configuration you need to set this attribute to the name of the yaml-file without the extension `yml`. The yaml file needs to be located in the hugo source directory `/poppygo/forms/[pogoform_id].yml` |

### Example form configuration

Below is a minimal form layout. You need to put `POGOFORM` in the form action
to use the pogoform.com-service.

```html
<form method="post" action="POGOFORM">
  <input type="hidden" name="POGOFORM_ID" value="contact-form-2">
  <input type="text" name="name" />
  <input type="text" name="email" />
  <textarea name="message" placeholder="Message"></textarea>
  <input type="submit" value="send" />
</form>
```

Below the configuration belonging to above form in the file
`poppygo/forms/contact-form-2.yml`

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
