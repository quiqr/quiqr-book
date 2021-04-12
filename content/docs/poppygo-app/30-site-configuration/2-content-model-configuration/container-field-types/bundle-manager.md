---
title: Bundle manager
---

# Bundle manager

The `bundle-manager` is a container field for creating a file-manager form for
managing the assets of page bundles. The word page bundle refers to [Hugo's
Page Bundles](https://gohugo.io/content-management/page-bundles/). A page
bundle is a way of organizing a page inside it's own directory together with
it's resources.

It's not possible to use Bundle managers with pages which are not stored as
page bundle.


{{< figure src="../bundle-manager1.png" caption="Bundle Manager together with a Bundle Image Thumbnail" >}}

{{< figure src="../bundle-manager2.png" caption="Bundle Manager with Bundle Image Thumbnail and extra string fields" >}}

## Bundle image thumbnail

The `bundle-image-thumbnail` field is a special field to be used together with
bundle-manager containers. It's creates preview image thumbnails of selected
images.

Read [bundle-image-thumbnail documentation]({{< ref path="../layout-field-types/bundle-image-thumbnail.md" >}}) for more information.

## Properties

| property | value type | optional  | description                                  |
|----------|------------|-----------|----------------------------------------------|
| key      | string     | mandatory | Keys are for internal use and must be unique |
| title    | string     | mandatory | The title of the element                     |

## Sample

### Configuration

```yaml
  key: images
  title: Images
  type: bundle-manager
  path: images
  extensions:
    - jpg
    - png
    - jpeg
    - pdf
    - svg
  fields:
    - key: thumb
      type: bundle-image-thumbnail
```

### Output

```
drwxr-xr-x    - poppy 25 Mar 10:09 content/portfolio/item2
drwxr-xr-x    - poppy 11 Apr 16:42 ├── images
.rw-r--r-- 198k poppy 19 Mar 14:43 │  ├── backgound-image.jpg
.rw-r--r-- 163k poppy 19 Mar 14:43 │  └── foregound-image.jpg
.rw-r--r--  148 poppy 11 Apr 16:42 └── index.md
```

## Known issues

A bug currently prevents the values of input fields to be saved in the frontmatter.
