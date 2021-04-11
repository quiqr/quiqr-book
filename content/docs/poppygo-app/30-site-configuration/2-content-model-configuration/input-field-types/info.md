---
title: Info
---

# Readonly

The `info` field is shows a readonly information box. It generates no output.

{{< figure src="../info.png" caption="Info field" >}}

## Properties

| property | value type | optional  | description                                          |
|----------|------------|-----------|------------------------------------------------------|
| key      | string     | mandatory | Keys are for internal use and must be unique         |
| content  | string     | mandatory | The content of the box in Markdown formatted textent |


## Sample

### Configuration

```yaml
  key: sample_field
  type: info
  content: |-
    # Info
    This is a readonly info field. You can use
    markdown for formatting
```

### Output

```yaml
sample_field: some value
```
