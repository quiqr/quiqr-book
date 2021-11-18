---
title: Anatomy of a PoppyGo Site
weight: 10
---

# Anatomy of a PoppyGo Site

## PoppyGo Data Directory

PoppyGo stores it's data in the ```Sukoh``` directory in the Home directory of the current user.

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

All PoppyGo sites store their top-level-configuration file in the root of the
PoppyGo Data Directory. This top-level-configuration file provides PoppyGo path
information to a PoppyGo website.

```bash
~/Sukoh/
  ./config.my-site.json
```

## Hugo and PoppyGo Site directory structure

```bas
./my_hugo_site/
  ./content/               (hugo content directory)
  ./static/                (hugo static files directory)
  ./data/                  (hugo data files directory)
  ./themes/                (hugo themes directory)
  ./resources/             (hugo temporary build resources directory)
  ./public/                (hugo final build directory)
  ./config.toml            (hugo main config file)
  ./.sukoh                 (poppygo thumbnails cache folder)
  ./poppygo/               (poppygo config folder)
     ./home/index.md       (optional message to the content editor in PoppyGo)
     ./forms/index.md      (forms end point configuration files)
     ./model/base.yaml     (main PoppyGo Model Configuration File)
     ./model/partials/     (directory with model configuration partials files)
     ./model/includes/     (directory with model configuration include files)
```

