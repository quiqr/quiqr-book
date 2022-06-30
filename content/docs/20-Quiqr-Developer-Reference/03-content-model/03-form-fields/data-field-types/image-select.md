---
title: Image Select
---

# Image Select

The `image-select` field creates a image selector picker field. It looks in a specified path for files to select.
The output is a string with the filename.

Only one image can be selected.

{{< figure src="../image-select1.png" caption="Image Select in form" >}}
{{< figure src="../image-select2.png" caption="Image Select dialog" >}}

## Properties

| property    | value type | optional                          | description                                                                                                                                                                                                                                                    |
|-------------|------------|-----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| key         | string     | mandatory                         | Keys are for internal use and must be unique                                                                                                                                                                                                                   |
| title       | string     | mandatory                         | The title of the element                                                                                                                                                                                                                                       |
| tip         | string     | optional (default: null)          | Text entered here with markdown formatting is displayed as context help in an overlay box                                                                                                                                                                      |
| default     | string     | optional (default: null)          | default value when the key is not set yet                                                                                                                                                                                                                      |
| autoSave    | boolean    | optional (default: false)         | Form data is automatically saved after changing the value                                                                                                                                                                                                      |
| path        | string     | mandatory                         | The path to the location of the files. When the path starts with `/` files are stored in the directory relative to the site root directory. Without a leading `/` files are stored in the directory relative to the where the markdown or data file is stored. |
| buttonTitle | string     | optional (default: "Select File") | Title of the button in the form.                                                                                                                                                                                                                               |

## Sample

### Configuration

{{< code-toggle file="./quiqr/model/base" >}}
key: sample_field
title: Sample field
type: image-select
path: /static/images
buttonTitle: select logo image
{{< /code-toggle >}}

### Output

```yaml
sample_field: logo.png
```
