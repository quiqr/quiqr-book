---
title: Markdown
---

# String

The `string` field generates a field for entering strings. Multiline string
values are allowed by enableing this property.

{{< figure src="../markdown1.png" title="Single markdown" >}}

{{< figure src="../markdown2.png" title="Multi line markdown" >}}

## Properties

| property  | value type | optional                 | description                                  |
|-----------|------------|--------------------------|----------------------------------------------|
| key       | string     | mandatory                | Keys are for internal use and must be unique |
| title     | string     | mandatory                | The title of the element                     |
| multiLine | boolean    | optional (default false) | Enable multi line value                      |
| preview   | boolean    | optional (default false) | Enable preview field with rendered HTML      |

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

## Known issues

The preview field is broken.
