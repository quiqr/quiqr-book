---
title: Date
---

# Date

The `date` field generates a date field with a date picker. The output value is
a date string.

{{< figure src="../date1.png" title="Date field" >}}
{{< figure src="../date2.png" title="Date picker popup" >}}

## Properties

| property | value type | optional                 | description                                                                               |
|----------|------------|--------------------------|-------------------------------------------------------------------------------------------|
| key      | string     | mandatory                | Keys are for internal use and must be unique                                              |
| title    | string     | mandatory                | The title of the element                                                                  |
| tip      | string     | optional (default: null) | Text entered here with markdown formatting is displayed as context help in an overlay box |
| default  | string     | optional (default: null) | default value when the key is not set yet                                                 |


## Sample

### Configuration

```yaml
  key: sample_field
  title: Sample field
  type: date
  default: "2021-04-12"
```

### Output

```yaml
sample_field: "2021-03-21"
```
