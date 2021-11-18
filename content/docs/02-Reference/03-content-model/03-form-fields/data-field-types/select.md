---
title: Select
---

# Select

The `select` field generates a dropdown selectbox for selecting strings or
numbers. The output is a number or string. If multiple is set true the out is
an array of numbers or strings.

{{< figure src="../select1.png" caption="Select field" >}}

{{< figure src="../select2.png" caption="Select multiple field" >}}

{{< figure src="../select3.png" caption="Select dropdown with options" >}}

## Properties

| property          | value type                            | optional                  | description                                                                               |
|-------------------|---------------------------------------|---------------------------|-------------------------------------------------------------------------------------------|
| key               | string                                | mandatory                 | Keys are for internal use and must be unique                                              |
| title             | string                                | mandatory                 | The title of the element                                                                  |
| tip               | string                                | optional (default: null)  | Text entered here with markdown formatting is displayed as context help in an overlay box |
| default           | string OR number OR  array of strings | optional (default: null)  | default value when the key is not set yet                                                 |
| multiple          | boolean                               | optional (default: false) | Enable multiple selection                                                                 |
| options           | array of dictionaries                 | mandatory                 | Array with title/value pairs                                                              |
| options.[n].text  | string                                | mandatory                 | String with option visible text                                                           |
| options.[n].value | string                                | mandatory                 | String with option value to save when selected                                            |


## Sample

### Configuration

{{< code-toggle file="./poppygo/model/base" >}}
key: sample_field
title: Sample field
type: select
multiple: false
default: 2
options:
  - text: Option 1
    value: 1
  - text: Option 2
    value: 2
  - text: Option 3
    value: 3
{{< /code-toggle >}}

### Output

```yaml
sample_field: 2
```

## Known issues

Default property is not working.
