---
title: Content Model Configuration
weight: 20
oxbookCollapseSection: true
---

# Content Model Confiration

PoppyGo can create advanced advanced models with customized forms for editing
any kind of content. These forms are configured in the ```./poppygo/model/``` directory
with ```base.json``` as the main configuration file. The model-files can be in
YAML, JSON or TOML-formatting.

## The file structure

The model file is split up in several main properties:

- **build**: information how to serve the hugo website
- **serve**: information how to build the hugo website
- **hugover**: the hugo version to use. The correct hugo version is downloaded automatically.
- **collections**: main key for collections with pages. E.g. _blog posts_
- **singles**: main key for single page configurations. E.g. _home page_ or _about_
- **menu**: main key for the menu configuration of the CMS.
- **dynamics**: main key for the dynamics form definitions to be used in dynamic forms.

## Single Properties

The Single main key is optional. It can define an array with one or more pages
or data files which will get their own navigation item in the PoppyGo Content
Menu. In the above example there is a Single page About configured and the
config.toml is also configured to be managed with PoppyGo. Below the properties of a
single Single dictionary.

| property   | value type                               | optional  | description                                                                                                  |
|------------|------------------------------------------|-----------|--------------------------------------------------------------------------------------------------------------|
| key        | string                                   | mandatory | Keys are for internal use and must be unique                                                                 |
| dataformat | string: yaml, toml,json                  | mandatory | Defines the type of output format. If _file_ is a markdown file the outputs regards to the frontmatter       |
| title      | string                                   | mandatory | The title of this page in the menu and when PoppyGo App refers to this page                                  |
| file       | string: relative path to file            | mandatory | The path to the file. This is the data storage. Can be data/somefile.{json,toml,yaml} or content/somefile.md |
| previewUrl | string: relative url path to the website | optional  | When set, this path is used to preview the page                                                              |
| fields     | array of dictionaries                    | mandatory | These are the form input fields.                                                                             |

## Collections Properties

The Collections main key is optional. It can define an array with one or more
collections with pages which will get their own navigation item in the PoppyGo
Content Menu. In the above example there is a Collection Blog configured
containing blog pages in the folder _content/blog/_. Below the properties of a
single collection dictionary.

| property   | value type                    | optional  | description                                                                                                                            |
|------------|-------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| key        | string                        | mandatory | Keys are for internal use and must be unique                                                                                           |
| dataformat | string: yaml, toml,json       | mandatory | Defines the output format of the frontmatter block. Collections can only handle markdown files. the outputs regards to the frontmatter |
| extension  | ???                           | mandatory | ???                                                                                                                                    |
| title      | string                        | mandatory | The title of this page in the menu and when PoppyGo App refers to this page                                                            |
| file       | string: relative path to file | mandatory | The path to the file. This is the data storage. Can be data/somefile.{json,toml,yaml} or content/somefile.md                           |
| itemtitle  | string                        | mandatory | The singular name of the collection items                                                                                              |
| folder     | string: relative path to dir  | mandatory | The path to the directory containing all files with the configured extension.                                                          |
| fields     | array of dictionaries         | mandatory | These are the form input fields.                                                                                                       |

## Menu Properties

The Menu main key is optional. When configured with an array of menu item
dictionaries, the PoppyGo content navigation is overriden by this
configuration. Without a configured menu, PoppyGo Creates two menu sections:
Singles and Collections. Below the properties of a single menu directory.

| property  | value type            | optional  | description                                  |
|-----------|-----------------------|-----------|----------------------------------------------|
| key       | string                | mandatory | Keys are for internal use and must be unique |
| title     | string                | mandatory | The title of this menu                       |
| menuItems | array of dictionaries | mandatory | contains a menu items                        |

Below the properties of a single menu item.

| property | value type | optional  | description                                                |
|----------|------------|-----------|------------------------------------------------------------|
| key      | string     | mandatory | this refers to the key of the defined Single of Collection |

## Model Input Fields

The main keys Singles, Collections and Dynamics can have fields definitions.
These are the building blocks for creating forms. Read more about in [model input fields]()




