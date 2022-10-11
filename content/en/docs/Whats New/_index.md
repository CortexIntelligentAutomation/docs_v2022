---
title: "What's New?"
linkTitle: "What's New?"
description: "Discover what's new in the Cortex Innovation platform."
weight: 1
---

## Improved Performance

This release introduces a [new engine][TODO: Feature] to execute automation solutions, and has shown [significant performance improvements][TODO: Feature] compared to 7.X, both in our own observations and customers installations. For example, one customer solution that has been migrated to 2022.9 has shown the time taken to run their tests reduce from 210 minutes to 10 minutes.

## Improved Availability

This release introduces a new [high availability (HA) architecture][TODO: Feature], which provides:

- Elimination of single points of failure resulting in reduced downtime
- The ability to perform zero downtime upgrades
- Increased processing capacity resulting in increased throughput

## Improved Usability

This release introduces:

- A quicker, [simplified installation process][TODO: Feature]
- A new [Package Management][TODO: Feature] system that improves the speed and ease of deploying automation solutions into production
- [180+ new blocks][TODO: Feature] to provide equivalent capability with the most used blocks within 7.X.
- A [new Property Editor][TODO: Feature] for configuring [blocks][block], allowing for quicker configuration and better ease of use.
- [Messages][TODO: Feature] which reports issues identified with a flow before it is executed
- A new online [Product Portal][TODO: Feature] that contains materials regarding the release and how to use the product
- Integration of [Cortex Studio][] with the [Product Portal][TODO: Feature]

## Improved Security

This release introduces the concept of [Encryptable and Encrypted text][TODO: Feature], allowing for blocks to identify and interact with sensitive data that should/must be encrypted at rest and during data transfer.

## Improved Observability

This release introduces:

- [Structured logging][TODO: Feature] providing a defined JSON format for [logs][reference: logs] produced by the Innovation Platform
- [Dashboards][] providing observability of the Innovation Platform in Production; these use [structured logs][TODO: Feature] as their source

## Other Improvements

This release introduces a number of other improvements, such as:

- [Flow Contracts][TODO: Feature] which allow a flow to declare any [Input Variables][] required to run the flow, and what [Output Variables][] will be returned by the flow
- [Debugging with Input Variables][TODO: Feature] which allow [flow developers][] to provide required [Input Variables][] when debugging a flow
- [Versioned APIs][TODO: Feature] which allow our APIs to evolve in future releases without breaking existing automation solutions

For a full list of what has been introduced in this release, please see the [2022.9 Release Notes][]
