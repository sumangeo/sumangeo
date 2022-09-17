---
# An instance of the Contact widget.
widget: contact

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 130

title: Contact
subtitle:

content:
  # Automatically link email and phone or display as text?
  autolink: true

  # Email form provider
  form:
    provider: netlify
    formspree:
      id:
    netlify:
      # Enable CAPTCHA challenge to reduce spam?
      captcha: false

 # Contact (edit or remove options as required)

email: suman.rubd@yahoo.com
contact_links:
  - icon: twitter
    icon_pack: fab
    name: Follow Me
    link: 'https://twitter.com/oporazito'
  - icon: skype
    icon_pack: fab
    name: Skype Me
    link: 'skype:suman.rbd?call'
design:
  columns: '2'
---
