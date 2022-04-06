---
title: Font Picker
---

# Font Picker

The `font-picker` field creates a font picker field populated by the Google
Fonts Api. The output is a string with a Font Family name.

{{< figure src="../font-picker.png" caption="Font Picker" >}}

## Properties

| property   | value type       | optional                 | description                                                                               |
|------------|------------------|--------------------------|-------------------------------------------------------------------------------------------|
| key        | string           | mandatory                | Keys are for internal use and must be unique                                              |
| title      | string           | mandatory                | The title of the element                                                                  |
| tip        | string           | optional (default: null) | Text entered here with markdown formatting is displayed as context help in an overlay box |
| default    | string           | optional (default: null) | default value when the key is not set yet                                                 |
| limit      | integer          | optional (default: 50)   | Max. amount of fonts to load, the most populair fonts are loaded                          |
| families   | array of strings | optional (default: null) | Array with Font Family names. If set, only these fonts are loaded                         |
| categories | array of strings | optional (default: null) | Array with Font Catogories. If set, only these fonts from these categories are loaded. "sans-serif", "serif", "display", "handwriting", "monospace"     |

## Sample

### Configuration

{{< code-toggle file="./quiqr/model/base" >}}
key: sample_field
title: Sample field
type: font-picker
default: roboto
families:
  - roboto
  - roboto condensed
  - lato
  - open sans
{{< /code-toggle >}}

### Output

```yaml
sample_field: lato
```

## Sample 2

### Configuration

{{< code-toggle file="./quiqr/model/base" >}}
key: sample_field
title: Sample field
type: font-picker
limit: 40
default: roboto
categories:
  - handwriting
{{< /code-toggle >}}

### Output

```yaml
sample_field: lato
```

## Credits

Font Picker is based on [Font Picker React](https://github.com/samuelmeuli/font-picker-react).
