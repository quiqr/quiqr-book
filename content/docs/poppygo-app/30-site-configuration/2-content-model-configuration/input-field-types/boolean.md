---
title: Boolean
---

# Boolean

The `boolean` field generates a switch. The output value is _true_ or _false_

{{< figure src="../boolean.png" title="Boolean" >}}

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
  type: boolean
```

### Output

```yaml
sample_field: true
```


## Sample frontmatter output

```yaml
```
