---
title: dynamics
weight: 70
---

# Root property: dynamics

The ```dynamics``` property is optional. Dynamics are used to dynamically mount
sub-forms in the accordion form field.

The dynamics property contains an array of dictionaries which itself it a form field definition.

## Example

{{< code-toggle file="model/base" >}}
dynamics:
  - key: component-banner
    component_type: banner
    fields:
      - key: bg_image
        title: Background image
        type: string
      - key: buttontxt
        title: Button text
        type: string
  - key: component-bullet-list
    component_type: bullet-list
    type: section
    groupdata: true
    fields:
      - key: text1
        title: Text 1
        type: string
      - key: text2
        title: Text 2
        type: string
      - key: text3
        title: Text 3
        type: string
{{< /code-toggle >}}

