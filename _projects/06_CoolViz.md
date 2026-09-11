---
layout: page
title: CoolViz
description: Interactive data-center visualization for identifying hotspots and evaluating workload-placement strategies.
img:
importance: 1
category: software
selected: false
related_publications: false
giscus_comments: false
---

## Overview

**CoolViz** is an interactive visualization system designed to help users understand how workloads affect temperature hotspots across a simulated data center.

The project started with a practical problem: data-center hotspots can contribute to degraded performance, outages, and equipment damage, while existing visualizations may not provide the temporal and workload context needed to understand how hotspots develop.

Our goal was to make this information easier to interpret and support more proactive decisions around workload placement and hotspot prevention.

Developed as a team project for **CSC 552: Advanced Operating Systems** at the **University of Arizona**.

## Problem

Data-center operators need to understand not only **where** hotspots occur, but also how temperature changes over time and how workload placement contributes to those changes.

We focused the project around three needs:

- Make hotspot behavior easy to identify visually
- Connect temperature information with workload and infrastructure context
- Support comparison of workload-placement strategies

## Product Approach

We designed CoolViz around progressively more detailed views so users could move from a high-level data-center view to individual server behavior.

The interface provides:

- **Data-center view** — shows the physical rack layout and average rack temperatures
- **Rack view** — shows servers within a selected rack and their temperatures
- **Server view** — shows the temperature of an individual server over time
- **Workload movement log** — shows transfers of jobs between racks
- **Time controls** — allow users to inspect how conditions change over time

This hierarchy was intended to keep the visualization understandable while still allowing deeper investigation when needed.

## System Design

We simulated a data center receiving web requests and distributing them across racks and servers.

The environment included:

- **28 racks**
- **10 servers per rack**
- **24 hours of workload data**
- Heavy, medium, and light web requests
- Temperature estimation based on workload and server characteristics
- Workload reassignment to simulate hotspot mitigation

We generated both normal and modified workload assignments so that the interface could be used to compare alternative operating strategies.

## Evaluation

We used CoolViz to compare temperature behavior under different workload-placement strategies.

The system supported analysis of:

- Temperature changes over time
- Hotspot locations
- Distribution of the hottest servers
- Frequency with which the hottest server changed
- Differences between normal and modified workload assignments

## Product Takeaways

CoolViz reinforced the importance of designing technical systems around the decisions users need to make rather than simply exposing all available data.

The project combined **systems thinking, data visualization, simulation, feature design, and iterative evaluation** to turn complex infrastructure data into a more interpretable user experience.
