---
title: Pogoforms
bookCollapseSection: true
weight: 20
---

# HTML Forms endpoint

A static website needs an external service for sending forms to e-mail. Sites
which are published to PoppyGo Cloud can use the `Pogoform` service for
sending e-mails. The configuration of the form-endpoint is done with a
yaml-file. And the HTML forms only need a simple action endpoint as
configuration.

**Requirements**:

* A working PoppyGo website published to the PoppyGo Cloud.

**Features**:

* Minimal configuration
* Privacy friendly, no cookies needed
* Multiple email address receivers
* Pogoform human check slider
* Server side validations

Read the [Pogoform Quickstart]({{< ref "./forms-quickstart" >}}) to get your form up
and running within 10 minutes.

The section [pogoform configuration properties]({{< ref
"./pogoform-properties" >}}) is a full reference for all options.

{{< figure src="./pogoform-slide.png" caption="Human test without palmtrees or traffic lights" >}}
