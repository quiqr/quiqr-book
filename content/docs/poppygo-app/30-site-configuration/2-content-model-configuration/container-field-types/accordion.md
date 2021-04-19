---
title: Accordion
---

# Accordion

The `accordion` field is a container field. It can define multiple input
fields, which are displayed as subform. The output is an array of dictionaries.

{{< figure src="../accordion.png" caption="Accordion" >}}

## Properties

| property              | value type                                               | optional  | description                                                                                                                                                                                                                                                                   |
|-----------------------|----------------------------------------------------------|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| key                   | string                                                   | mandatory | Keys are for internal use and must be unique                                                                                                                                                                                                                                  |
| title                 | string                                                   | mandatory | The title of the accordion element                                                                                                                                                                                                                                            |
| dynFormSearchKey      | string                                                   | optional (default: null)  | key of one of the child field of which the value refers to a custom partial form                                                                                                                                                                                              |
| dynFormObjectFile     | string with relative path to file without file extension | optional (default: null)  | if dynFormSearchKey is set this path points to the file containing a subform. **Do not define the used file extension**. PoppyGo will automatically try to open json, toml or yaml files. If dynFormObjectFile is not set it refers to the partials in the sukoh file itself. |
| dynFormObjectRoot     | string                                                   | optional (default: null) | if dynFormObjectFile is set this points to the root node where the subform is defined e.g. components                                                                                                                                                                         |
| fields                | array of dictionaries                                    | mandatory | These are the form input fields.                                                                                                                                                                                                                                              |
| fields.[n].arrayTitle | boolean                                                  | optional (default: false) | The value of the child field which has arrayTitle=true will be displayed as the accordion item title                                                                                                                                                                          |

## Regular accordion

Below an example of a regular accordion configuration without dynamic forms.

{{< code-toggle file="sukoh" >}}
key: my-accordion
title: "accordion"
type: "accordion"
fields:
  - key: title
    title: Title
    type: string
    arrayTitle: true
  - key: boolean1
    title: boolean1
    type: boolean
  - key: boolean2
    title: boolean2
    type: boolean
  - key: boolean3
    title: boolean3
    type: boolean
{{< /code-toggle >}}

## Accordion with dynamic forms defined in sukoh.yaml

Fragments of the `sukoh.yaml` with a dynamic accordion and a  partials section

{{< code-toggle file="sukoh" >}}
key: page_sections
title: Page sections
type: accordion
dynFormSearchKey: component_type
fields:
  - key: title
    title: Title
    type: string
    arrayTitle: true
  - key: component_type
    title: Component Type
    type: select
    multiple: false
    options:
      - text: Component 1
        value: component1
      - text: Component 2
        value: component2
{{< /code-toggle >}}

{{< code-toggle file="sukoh" >}}
partials:
  - key: component1
    component_type: poppy-banner
    fields:
      - key: poppy_variant
        title: PoppyGo Variant
        type: select
        multiple: false
        options:
          - text: Full height
            value: header-banner-full-height
          - text: Regular
            value: header-banner
      - key: bg_image
        title: Background image
        type: string
      - key: buttontxt
        title: Button text
        type: string
  - key: component2
    component_type: poppy-shortlist
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

## Accordion with dynamic forms defined in a seperate file

Fragments of the `sukoh.yaml` with a dynamic accordion.

{{< code-toggle file="sukoh" >}}
key: page_sections
title: Page sections
type: accordion
dynFormSearchKey: component_type
dynFormObjectFile: data/pageComponentsTree
dynFormObjectRoot: components
fields:
  - key: title
    title: Title
    type: string
    arrayTitle: true
  - key: component_type
    title: Component Type
    type: select
    multiple: false
    options:
      - text: Component 1
        value: component1
      - text: Component 2
        value: component2
{{< /code-toggle >}}

The complete object file in this case `data/pageComponentsTree.yaml`

{{< code-toggle file="sukoh" >}}
components:
  - key: component1
    component_type: poppy-banner
    fields:
      - key: poppy_variant
        title: PoppyGo Variant
        type: select
        multiple: false
        options:
          - text: Full height
            value: header-banner-full-height
          - text: Regular
            value: header-banner
      - key: bg_image
        title: Background image
        type: string
      - key: buttontxt
        title: Button text
        type: string
  - key: component2
    component_type: poppy-shortlist
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
