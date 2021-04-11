---
title: String
---

# String

The `string` field generates a field for entering strings. Multiline string
values are allowed by enableing this property.

{{< figure src="../string1.png" title="Single line string" >}}

{{< figure src="../string2.png" title="Multi line string" >}}

## Properties

| property  | value type | optional                 | description                                  |
|-----------|------------|--------------------------|----------------------------------------------|
| key       | string     | mandatory                | Keys are for internal use and must be unique |
| title     | string     | mandatory                | The title of the element                     |
| multiLine | boolean    | optional (default false) | Enable multi line value                      |

## Sample

### Configuration

```yaml
  key: sample_field
  title: Sample field
  type: string
  multiLine: true
```

### Output

```yaml
sample_field: |-
  Some multiline
  string value
```
