---
title: 'Send a Message'
form:
  name: contact
  fields:
    name:
      label: 'Full Name'
      placeholder: 'Your name'
      type: text
      validate:
        required: true
    email:
      label: 'Email Address'
      placeholder: 'you@company.com'
      type: email
      validate:
        required: true
    phone:
      label: 'Phone (optional)'
      placeholder: '+92 3xx xxxxxxx'
      type: text
    message:
      label: 'Message'
      placeholder: 'Tell me a bit about your business and what you need'
      type: textarea
      validate:
        required: true
    honeypot:
      type: honeypot

  buttons:
    submit:
      type: submit
      value: 'Send Message'

  process:
    - action: email
      params:
        to: 'mas@amersaeed.com'
        subject: "[amersaeed.com] New enquiry from {{ form.value.name|e }}"
        body: "{% include 'forms/data.html.twig' %}"
    - action: message
      message: 'Thanks for reaching out — I will get back to you within a day or two.'
    - action: redirect
      redirect: /contact
---

## Or Send a Message
