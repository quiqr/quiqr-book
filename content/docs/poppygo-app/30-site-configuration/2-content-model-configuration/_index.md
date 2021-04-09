---
title: Content Model Configuration
weight: 20
---

# Content Model Confiration

For content managing PoppyGo App can create advanced forms to edit content. These
forms are configured in the _sukoh.json file_. The sukoh-file can be in YAML,
JSON or TOML-formatting. For sake of readability we use YAML for inline example
snippets in this reference.

## Sukoh file structure.

The sukoh file is split up in several main properties:

- **build**: information how to serve the hugo website
- **serve**: information how to build the hugo website
- **hugover**: the hugo version to use. The correct hugo version is downloaded automatically.
- **collections**: main key for collections with pages. E.g. _blog posts_
- **singles**: main key for single page configurations. E.g. _home page_ or _about_
- **menu**: main key for the menu configuration of the CMS.
- **partials**: main key for the partial form definitions to be used in dynamic forms.

Here's an example sukoh.yaml file containing a minimal configuration for a blog website.

```yaml
build:
  - config: config.toml
    key: default
serve:
  - config: config.toml
    key: default
hugover: extended_0.76.5
collections:
  - dataformat: yaml
    extension: md
    fields:
      - key: draft
        title: Draft
        type: boolean
      - key: title
        title: Title
        type: string
      - extensions:
          - jpg
          - png
          - jpeg
          - pdf
          - svg
        fields:
          - key: thumb
            title: Thumb
            type: bundle-image-thumbnail
        key: page_related_images
        path: ''
        title: Page related images
        type: bundle-manager
      - key: mainContent
        title: Main content
        type: markdown
      - key: publishdate
        title: Publishdate
        type: hidden
      - key: tags
        title: Tags
        type: chips
    folder: content/post/
    itemtitle: Post
    key: c__post
    title: Posts
menu:
  - key: singles
    menuItems:
      - key: s__about
    title: Pages
  - key: collections
    menuItems:
      - key: c__post
    title: Groups
  - key: general
    menuItems:
      - key: config
    title: General
singles:
  - dataformat: toml
    fields:
      - key: description
        title: Description
        type: string
      - key: title
        title: Title
        type: string
      - fields:
          - key: author
            title: Author
            type: string
          - key: dateFormat
            title: Date format
            type: string
          - key: description
            title: Description
            type: string
          - key: paginationSinglePost
            title: Pagination single post
            type: boolean
          - key: readMore
            title: Read more
            type: boolean
          - key: style
            title: Style
            type: string
        groupdata: true
        key: params
        title: Params
        type: section
    file: config.toml
    key: config
    title: Settings
  - dataformat: yaml
    fields:
      - key: title
        title: Title
        type: string
      - key: description
        title: Description
        type: string
      - extensions:
          - jpg
          - png
          - jpeg
          - pdf
          - svg
        fields:
          - key: thumb
            title: Thumb
            type: bundle-image-thumbnail
        key: page_related_images
        path: images/
        title: Page related images
        type: bundle-manager
      - key: mainContent
        title: Main content
        type: markdown
    file: content/about.md
    key: s__about
    previewUrl: /about/
    title: About
```

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

## Form Input Components

the main keys Singles, Collections and Partials can have fields definitions.
These are the building blocks for creating forms.




