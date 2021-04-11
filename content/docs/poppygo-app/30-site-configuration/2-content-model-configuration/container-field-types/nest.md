---
title: Nest
---

# Nest


The `nest` field is a container field. It can define multiple input fields,
which are displayed as a subform. You have to focus the nest-field the show the
sub form. The output is a dictionary with values from
the sub form fields.

{{< figure src="../nest1.png" title="nest unfocussed" >}}

{{< figure src="../nest2.png" title="nest focussed" >}}

## Properties

### Bundle manager Properties

| property  | value type            | optional                 | description                                   |
|-----------|-----------------------|--------------------------|-----------------------------------------------|
| key       | string                | mandatory                | Keys are for internal use and must be unique. |
| title     | string                | mandatory                | The title of the element.                     |
| fields    | array of dictionaries | mandatory                | These are the subform input fields.           |
| groupdata | boolean               | optional (default false) | ??                                            |

## Sample

### Configuration

```yaml
  key: some_parent_field
  title: Some parent field
  type: nest
  groupdata: true
  fields:
  - key: some_child_field
    title: Some chield field
    type: date
```

### Output

```yaml
some_parent_field:
  some_child_field: "2021-04-02"
```
