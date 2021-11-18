---
title: Partials
weight: 10
---

# Partials

Partials are reusable configuration blocks that can be used in a form
definition inside singles, collections and dynamics.

Partials can be used with the property ```_mergeFromPartial```. The value of
this property is a string with the name of the partial file without it's
extension.

Partials are merged with to other form attributes. Attributes which are also
defined in the form with overwrite the partial attributes.

## Example

In ```./model/base.yaml``` a form definition in ```singles``` points to ```minimal_configuration```.

### The base

```./model/base.yaml```
```yaml
singles:
  - key: config
    file: config.toml
    title: Settings
    _mergeFromPartial: minimal_configuration
```

### The partial

```./model/partial/minimal_configuration.yaml```
```yaml
- dataformat: yaml
  fields:
    - key: title
      title: Title
      type: string
    - key: description
      title: Description
      type: string
    - key: theme
      theme: Theme
      type: string
  title: Minimal Configuration
```

### The compiled end result

```yaml
singles:
  - key: config
    file: config.toml
    title: Settings
    dataformat: yaml
    fields:
      - key: description
        title: Description
        type: string
      - key: title
        title: Title
        type: string
      - key: theme
        theme: Theme
        type: string
```

{{< hint info >}}
The title or the partial *Minimal Configuration* is overwritten the the calling
definition in ```base.yml```, leaving it *Settings*.
{{< /hint >}}


