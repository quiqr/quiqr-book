---
title: Info
---

# Info

The `info` field is shows a readonly information box. It generates no output.

{{< figure src="../info.png" caption="Info field" >}}

## Properties

| property | value type                             | optional                   | description                                          |
|----------|----------------------------------------|----------------------------|------------------------------------------------------|
| key      | string                                 | mandatory                  | Keys are for internal use and must be unique         |
| content  | string                                 | mandatory                  | The content of the box in Markdown formatted textent |
| size     | enum of strings (normal, small, large) | optional (default: normal) | Fontsize of small is 85%, normal 100%, large 110%    |


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
