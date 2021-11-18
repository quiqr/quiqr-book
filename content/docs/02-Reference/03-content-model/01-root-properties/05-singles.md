---
title: single
weight: 50
---

# Root property: singles

The ```singles``` property is optional. When defined Singles containes an array
of dictionaries. Every dictionary defines a single form to edit a single file.
The file can be located anywhere in the site directory structure but typically
points to a file in the root directory, the content directory or the data
directory of a hugo project.

These are the properties of a Single dictionary.

| property   | value type                               | optional  | description                                                                                                  |
|------------|------------------------------------------|-----------|--------------------------------------------------------------------------------------------------------------|
| key        | string                                   | mandatory | Keys are for internal use and must be unique                                                                 |
| dataformat | string: yaml, toml,json                  | mandatory | Defines the type of output format. If _file_ is a markdown file the outputs regards to the frontmatter       |
| title      | string                                   | mandatory | The title of this page in the menu and when PoppyGo App refers to this page                                  |
| file       | string: relative path to file            | mandatory | The path to the file. This is the data storage. Can be data/somefile.{json,toml,yaml} or content/somefile.md |
| previewUrl | string: relative url path to the website | optional  | When set, this path is used to preview the page                                                              |
| fields     | array of dictionaries                    | mandatory | These are the form input fields.                                                                             |

## Example

{{< code-toggle file="./model/base" >}}
singles:
  - dataformat: toml
    fields:
      - key: description
        title: Description
        type: string
      - key: title
        title: Title
        type: string
    file: config.toml
    key: config
    title: Settings
{{</ code-toggle  >}}
