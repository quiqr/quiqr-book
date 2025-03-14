---
title: Select from Query
---

# Select from Query

**Quiqr version >= 0.16.0**

The `select-from-query` field generates a dropdown selectbox for selecting
strings generated by an query string.

**IMG TODO**

## Properties

| property               | value type                 | optional                  | description                                                                                           |
|:-----------------------|----------------------------|---------------------------|-------------------------------------------------------------------------------------------------------|
| key                    | string                     | mandatory                 | Keys are for internal use and must be unique                                                          |
| title                  | string                     | optional                  | The title of the element                                                                              |
| tip                    | string                     | optional (default: null)  | Text entered here with markdown formatting is displayed as context help in an overlay box             |
| default                | string OR array of strings | optional (default: null)  | default value when the key is not set yet                                                             |
| multiple               | boolean                    | optional (default: false) | Enable multiple selection                                                                             |
| autoSave               | boolean                    | optional (default: false) | Form data is automatically saved after changing the value                                             |
| query_glob             | string                     | mandatory                 | Glob string to select one or more files                                                               |
| query_string           | string                     | mandatory                 | string to use on one the of the query types                                                           |
| option_image_path      | string                     | optional (default: null)  | path to images having the same name as the options values e.g. `quiqr/model/images`                   |
| option_image_width     | number                     | optional (default: null)  | when `option_image_path` is set image width as well to have a aligned option listing                  |
| option_image_extension | string                     | optional (defaul: null)   | when `option_image_path` is set, optionally set extension to e.g. `jpg`. Then all images should be of type `jpg`. |

## Example 1

This example shows a simple query.

### Configuration

{{< code-toggle file="./quiqr/model/base" >}}
key: sample_field
title: Sample field
type: select-from-query
multiple: false
default: 2
query_glob: data/system_data.json
query_string: .weekday[]
{{< /code-toggle >}}

### Output

options:
- Monday
- Tuesday
- ...

possible frontmatter result
```yaml
sample_field: Monday
```

## Example 2

This example shows a simple query together with image visualization.

{{< figure src="../select_visual.png" caption="Select field" >}}

### Configuration

{{< code-toggle file="./quiqr/model/base" >}}
key: sample_field
title: Sample field
type: select-from-query
multiple: false
default: 2
query_glob: data/system_data.json
query_string: .weekday[]
option_image_path: ./quiqr/model/images
option_image_width: 200
option_image_extension: jpg

{{< /code-toggle >}}

### Output

options:
- Monday
- Tuesday
- ...

possible frontmatter result
```yaml
sample_field: Monday
```

## Query Language

The Quiqr Query Language is inspired by JQ, but has some additions specially
suited for querying the Hugo content. Currently this page contains all
information about QQL.

QQL selects data or metadata from markdown/json/yaml/toml files.

In the select-from-quert field, only results in the form of arrays with strings
are valid. Other results types wil produce an error message.

At time of writing QQL only exists in this document. QQL is in a very early
development phase.

When the query_string starts with `#` the file meta data will be queried.
When the query_string starts with `.` the file content data will be queried.

## Meta data functions

- **file_name**: returns the full filename-component. e.g. `blog-about-quiqr.md`
- **file_base_name**: returns the filename with out extension. e.g. `blog-about-quiqr`
- **parent_dir**: returns the parent directory of the found filename with out extension. e.g. `the-post` when the filename is a bundle posts/the-post/index.md

### Populating select option with filenames from a directory.

```yaml
query_glob: content/resources/*.md
query_string: "#file_name[]"
```

### Populating select option with titles from front matter from multiple directories.

```yaml
query_glob: content/**/*.md
query_string: .title[]
```

## Known issues

WIP
