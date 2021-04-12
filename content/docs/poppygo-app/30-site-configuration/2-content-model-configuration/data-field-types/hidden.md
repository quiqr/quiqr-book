---
title: Hidden
---

# Hidden

The `hidden` field is hidden for the user but outputs a default value.

## Properties

| property | value type | optional  | description                                  |
|----------|------------|-----------|----------------------------------------------|
| key      | string     | mandatory | Keys are for internal use and must be unique |
| default  | string     | mandatory | default value when the key is not set yet    |


## Sample

### Configuration

```yaml
  key: sample_field
  default: some value
  type: hidden
```

### Output

```yaml
sample_field: some value
```
