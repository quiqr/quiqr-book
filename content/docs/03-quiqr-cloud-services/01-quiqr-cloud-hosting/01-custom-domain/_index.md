---
title: Custom Domain
weight: 10
---

# Custom Domain

## Step 1: Upgrade & connect domain

To connect your site to a custom domain your should upgrade your Quiqr Plan.
Follow instructions inside your Quiqr Desktop Application.

## Step 2: Change DNS of your domain

When the domain is connected in the Quiqr App, you should finally change the
DNS of your domain.

To change the DNS of your domain you should login to the Dashboard of your
Domain registry. Find the `DNS` or `Nameserver` page in the menu and edit the
following records.

| name | type | value         |
|------|------|---------------|
| @    | A    | 99.81.100.114 |
| @    | AAAA | 99.81.100.114 |
| www  | A    | 99.81.100.114 |
| www  | AAAA | 99.81.100.114 |
