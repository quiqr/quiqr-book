---
title: Date
---

# Date

The `date` field generates a date field with a date picker. The output value is
a date string.

{{< figure src="../date1.png" title="Date field" >}}
{{< figure src="../date2.png" title="Date picker popup" >}}

## Properties

| property | value type | optional  | description                                  |
|----------|------------|-----------|----------------------------------------------|
| key      | string     | mandatory | Keys are for internal use and must be unique |
| title    | string     | mandatory | The title of the element                     |


## Sample

### Configuration

```yaml
  key: sample_field
  title: Sample field
  type: date
```

### Output

```yaml
sample_field: "2021-03-21"
```
