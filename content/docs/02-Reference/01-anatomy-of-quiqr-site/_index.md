---
title: Anatomy of a Quiqr Site
weight: 10
---

# Anatomy of a Quiqr Site

## Quiqr Data Directory

Quiqr stores it's data in the ```Sukoh``` directory in the Home directory of the current user.

### Sukoh on Windows

```batch
C:\Users\robin\Sukoh
```

### Sukoh on macOS

```bash
/Users/robin/Sukoh
```

### Sukoh on Linux/BSD

```bash
/home/robin/Sukoh
```

## Site configuration

All Quiqr sites store their top-level-configuration file in the root of the
Quiqr Data Directory. This top-level-configuration file provides Quiqr path
information to a Quiqr website.

```bash
~/Sukoh/
  ./config.my-site.json
```

## Hugo and Quiqr Site directory structure

```bas
./my_hugo_site/
  ./content/               (hugo content directory)
  ./static/                (hugo static files directory)
  ./data/                  (hugo data files directory)
  ./themes/                (hugo themes directory)
  ./resources/             (hugo temporary build resources directory)
  ./public/                (hugo final build directory)
  ./config.toml            (hugo main config file)
  ./.sukoh                 (quiqr thumbnails cache folder)
  ./quiqr/               (quiqr config folder)
     ./home/index.md       (optional message to the content editor in Quiqr)
     ./forms/index.md      (forms end point configuration files)
     ./model/base.yaml     (main Quiqr Model Configuration File)
     ./model/partials/     (directory with model configuration partials files)
     ./model/includes/     (directory with model configuration include files)
```

