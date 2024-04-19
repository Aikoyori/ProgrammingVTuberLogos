---
name: Logo Requests
about: For requesting logos
title: "[LOGO REQUEST]"
labels: Logo Request
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
      label: Product Name
      description: The product you want the logo to be made
      placeholder: Acme Explosive Eggs
      required: true
  - type : input
    id: product-link
    attributes:
      label: Product Link
      description: The link to the product
      placeholder: https://example.com
      required: false
  - type : textarea
    id: additional-info
    attributes:
      label: Other information
      description: Describe the product and the logo you want
      placeholder: The logo should be made with with Acme color scheme.
      required: false
  - type: checkboxes
    id: agreement
    attributes:
      label: The following is required to submit this issue
      description: By submitting this issue, you agree that these logos will be made available under the project's license and that you have checked if the logo is already available or already requested.
      options:
        - label: I agree that the logo will be made available under the project's license
          required: true
        - label: I have checked that I am not making a duplicate request
          required: true
---
