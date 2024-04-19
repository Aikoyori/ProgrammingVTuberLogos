---
name: README additions
about: Additions to READMe.md
title: "[README] "
labels: README additions
assignees: Aikoyori

body:
  - type: markdown
  - attributes:
    value: |
      # Thanks for your interest!
      Please provide the following information:
  - type : input
    id: product-name
    attributes:
      label: Your Repo Link
      description: The product you want the logo to be made
      placeholder: Acme Logos
      required: true
  - type : textarea
    id: additional-info
    attributes:
      label: Other information
      description: Describe the product and the logo you want
      placeholder: The logos of Acme as additions.
      required: false
  - type: checkboxes
    id: agreement
    attributes:
      label: The following is required to submit this issue
      description: By submitting this issue, you have checked if the logo is already available or already requested.
      options:
        - label: I have checked that I am not making a duplicate request
          required: true
---


