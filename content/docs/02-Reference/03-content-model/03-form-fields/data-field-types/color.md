---
title: Color
---

# String

The `color` field generates a colorpicker for entering color hex codes.

{{< figure src="../color1.png" caption="Color picker popup" >}}

## Properties

| property  | value type | optional                  | description                                                                               |
|-----------|------------|---------------------------|-------------------------------------------------------------------------------------------|
| key       | string     | mandatory                 | Keys are for internal use and must be unique                                              |
| title     | string     | mandatory                 | The title of the element                                                                  |
| tip       | string     | optional (default: null)  | Text entered here with markdown formatting is displayed as context help in an overlay box |

## Sample

### Configuration

{{< code-toggle file="./poppygo/model/base" >}}
key: sample_field
title: Sample field
type: color
{{< /code-toggle >}}

### Output

```yaml
sample_field: #ccee00
```
