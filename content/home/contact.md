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
    provider: formspree
    formspree:
      id: xaykelvr
      # Enable CAPTCHA challenge to reduce spam?
      captcha: false

# Contact details (edit or remove options as required)
  contact_links:
    - icon: twitter
      icon_pack: fab
      name: Follow Me
      link: 'https://twitter.com/oporazito'
    - icon: facebook
      icon_pack: fab
      name: Facebook
      link: 'https://facebook.com/SumanGeo'
    - icon: whatsapp
      icon_pack: fab
      name: Whatsapp
      link: 'https://wa.me/8801521500081/?text=Hi'
    - icon: globe
      icon_pack: fas
      name: EGIT Solutions
      link: 'https://sites.google.com/view/egitsolutions'      
    - icon: globe
      icon_pack: fas
      name: PGDICT43
      link: 'https://pgdict43.netlify.app'

design:
  # Choose how many columns the section has. Valid values: '1' or '2'.
  columns: '2'
---
