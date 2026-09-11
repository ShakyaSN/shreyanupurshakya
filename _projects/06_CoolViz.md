---
layout: page
title: CoolViz
description: Interactive visualization of data-center workloads and temperature hotspots.
img: /assets/img/coolviz/coolviz-overview.png
importance: 1
category: software
selected: false
related_publications: false
giscus_comments: false
---

**CoolViz** is an interactive visualization system for exploring temperature hotspots in simulated data-center environments.

Data-center hotspots can contribute to degraded performance, outages, and equipment damage. CoolViz was designed to make hotspot behavior easier to understand and support timely decisions about workload placement and cooling.

Developed as a team project for **CSC 552: Advanced Operating Systems** at the **University of Arizona**.

## System Design

We simulated a data center receiving web requests as workload and distributing those requests across racks and servers. Server temperatures were estimated based on workload, power consumption, server position, and incoming cooling conditions.

The simulated environment included:

- **28 racks** arranged across four rows
- **10 servers per rack**
- **24 hours of workload data**
- Heavy, medium, and light web requests
- Workload reassignment to simulate hotspot mitigation

## Interactive Visualization

CoolViz provides multiple levels of visualization for examining temperature behavior across the simulated data center.

<div class="row">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/coolviz/rack-room.png" title="Data center rack visualization" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/coolviz/server-temperature.png" title="Server temperature visualization" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
CoolViz visualizes temperature at multiple levels, from the data-center rack layout to individual server behavior over time.
</div>

The interface includes:

- **Data-center view** — rack layout and average rack temperatures
- **Rack view** — individual servers and their average temperatures
- **Server view** — temporal temperature behavior for a selected server
- **Workload movement log** — transfers of jobs between racks
- **Time controls** — stepping through temperature changes over time

## Comparing Workload Strategies

We compared normal workload assignment with modified workload placement designed to reduce hotspots.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/coolviz/comparison.png" title="Comparison of workload placement strategies" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
Comparison of temperature behavior under different workload-placement strategies.
</div>

The visualization supports analysis of:

- Temperature behavior across workload-placement strategies
- Changes in the hottest server over time
- Distribution of hotspot locations
- Temporal temperature patterns

## Outcome

CoolViz demonstrates how workload, infrastructure structure, and temporal temperature data can be combined in an interactive interface to make data-center hotspot behavior easier to analyze.
