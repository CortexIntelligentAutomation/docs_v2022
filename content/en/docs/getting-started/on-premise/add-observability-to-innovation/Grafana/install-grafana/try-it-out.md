---
title: "Try it Out"
linkTitle: "Try it Out"
description: "Information about trying out Grafana after configuration."
weight: 30
---

# {{< param title >}}

This guide describes how to try out Grafana after configuration to make sure it is working.

## Verify That HTTPS Works

It is important to verify that Grafana is accessible only though HTTPS and not HTTP connection.

1. On the Web Application Server open a web browser.
1. Browse to `http://localhost:3000/`.
1. Browser should not be able to make a connection to Grafana and a default error page should be displayed.
1. Browse to `https://localhost:3000/`.
1. On the login page, enter `admin` and the corresponding password.
1. Click Log in.
1. You should have successfully logged into Grafana.
