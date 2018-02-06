# gutenberg-punchcutter
Quickly create dynamic WordPress Gutenberg blocks

## Goal
Generate code for WordPress Gutenberg blocks based on configuration files. Use BEM principles to generate dynamic user content.

## Provisional example

``` yaml
blocks:
  - name: quote
    displayname: Quote
    icon: quote
    modifiers:
      - name: dark
        description: Use the high contrast version
        type: boolean
    elements:
      - name: title
        displayname: Title
        element: h1
        modifiers: 
          - name: muted
            description: Show a muted version of the quote
            type: boolean
          - name: align
            description: Align the element
            type: select
            options:
              - name: left
                displayname: Left
              - name: right
                displayname: Right
      - name: content
        element: p
        displayname: Content
```

The following would create a block like the following:

``` html
<div class='quote quote--dark'>
   <h1 class='quote__title quote__title--muted quote__title--align-left'>Example title</h1>
   <p class='quote__content'>Example content</p>
</div>
```
