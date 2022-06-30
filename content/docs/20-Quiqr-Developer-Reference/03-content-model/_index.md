---
title: Content Model
weight: 40
bookCollapseSection: true
---

# Content Model Configuration

Quiqr can create advanced advanced models with customized forms for editing
any kind of content. These forms are configured in the ```./quiqr/model/``` directory
with ```base.json``` as the main configuration file. The model-files can be in
YAML, JSON or TOML-formatting.

## Root Properties

The model is split up in several main properties:

- **build**: information how to serve the hugo website
- **serve**: information how to build the hugo website
- **hugover**: the hugo version to use. The correct hugo version is downloaded automatically.
- **collections**: main key for collections with pages. E.g. _blog posts_
- **singles**: main key for single page configurations. E.g. _home page_ or _about_
- **menu**: main key for the menu configuration of the CMS.
- **dynamics**: main key for the dynamics form definitions to be used in dynamic forms.

## Model File Structure

Quiqr has helpers two organize complex models and prevent redundant
configuration code. ```Includes``` are used to split the main-file into
seperate files and partials makes it possible to reuse configuration code.

## Form Fields

The main keys Singles, Collections and Dynamics can have form fields definitions.
These are the building blocks for creating forms.




