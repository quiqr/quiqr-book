---
title: Top Level Site Config File
weight: 10
xbookToc: false
---

# Site configuration File

Every Quiqr website has a top-level configuration file. It's located in
```$HOME/Sukoh/config.websitename.json```.
The site configurations tells Quiqr where to find the site files and where to
publish the website.

{{< hint warning >}}
The site files are maintained by Quiqr and should not be edited manually,
except when you know whhat you're doing.
{{< /hint >}}

| property                       | value type            | optional  | description                                                          |
|--------------------------------|-----------------------|-----------|----------------------------------------------------------------------|
| key                            | string                | mandatory | Keys are for internal use and must be unique                         |
| name                           | string                | mandatory | The name of the website                                              |
| lastPublish                    | integer               | mandatory | Timespamp with time of last publication                              |
| publishStatus                  | integer               | mandatory | 1=published, 2=publication pending remote                            |
| source.type                    | string                | mandatory | Depriciated: Should always be _folder_                               |
| source.path                    | string                | mandatory | Path to the Hugo site root directory                                 |
| publish                        | array of dictionaries | mandatory | Array with publish configurations, currently only one is supported   |
| publish.0.key                  | string                | mandatory | Keys are for internal use and must be unique                         |
| publish.0.config               | dictionary            | mandatory | Dictionary with publish configuration information                    |
| publish.0.config.type          | string                | mandatory | type publication endpoint. Currently only poppygo-cloud is supported |
| publish.0.config.defaultDomain | string                | mandatory | default live domain                                                  |
