---
title: Chips
---

# Chips

The `chips` field generates a field that helps creating tags of keywords from
entered strings instantly. The output value is an array with strings.

{{< figure src="../chips.png" title="Chips" >}}

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
  type: chips
```

### Output

```yaml
sample_field:
  - tag 1
  - tag 2
```
