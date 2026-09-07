---
layout: page
title: EMC/EMI & Side-Channel Analysis
description: electromagnetic reliability, security, and signal/power integrity
img: assets/img/projects/project_emc.png
importance: 2
category: application
research_id: emc
permalink: /projects/emc/
related_publications: true
---

Modern electronic systems contain densely integrated PCBs, ICs, packages, interconnects, antennas, and nonlinear circuit components operating within a shared electromagnetic (EM) environment. Unintended EM interactions can lead to interference, degraded system performance, and device vulnerability, while the same EM emissions may also carry useful information about internal circuit activity.

Our research develops **full-wave computational and experimental approaches for electromagnetic compatibility (EMC), interference (EMI), and side-channel analysis (SCA)**. The numerical framework draws upon our work on [domain decomposition methods](/projects/ddm/), [hierarchical direct solvers](/projects/direct_solver/), and [EM-circuit co-simulation](/projects/mphy/), while laboratory measurements provide direct validation and characterization of practical electronic systems.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/emc/emc_cyan.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>

<div class="caption">
    Overview of computational and experimental EMC research: EM emissions, vulnerability, RF/microwave measurements, and side-channel applications.
</div>


## Electromagnetic Emissions & Side Channels

EM emissions from electronic circuits are traditionally treated as an EMC concern because unintended radiation can interfere with nearby components and systems. At the same time, these emissions contain information about the electrical activity and physical characteristics of the underlying hardware.

Our research investigates this dual role of EM radiation. Full-wave modeling and measurements are used to characterize externally observable EM responses of electronic systems. The resulting emission signatures can support not only EMC assessment, but also **side-channel analysis, device characterization, and hardware authentication**.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/emc/emc_ic_emission.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    <!-- Overview of near-field emission measurement and full-wave modeling of practical PCB and IC systems. -->
    EM emissions as signatures for circuit characterization, side-channel analysis, and hardware authentication.
</div>

Accurate utilization of these emissions requires their spatial and frequency-dependent characteristics to be understood. We therefore combine full-wave simulations with controlled near-field measurements to compare field distributions, identify **emission hot spots and dominant radiation regions**, and quantify the influence of practical measurement probes.

The PCB-emission work explicitly models the probe together with the device under test rather than treating the probe as an ideal observer, so that probe–PCB interactions are incorporated directly into the comparison between simulation and measurement. 

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/emc/emc_ic_emission_res.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>

<div class="caption">
    Near-field emission characterization through simulation and measurement, including field distributions, emission hot-spot tracing, and the effects of practical probe geometries.
</div>


## Electromagnetic Interference & Vulnerability

The complementary EMC problem concerns how electronic systems respond to **external electromagnetic interference (EMI)**. Incident fields may couple through PCB traces, interconnects, connectors, packages, and other structures before reaching sensitive circuit components. Accurate vulnerability assessment therefore requires both the propagation of EM fields through the physical system and the resulting electrical responses of the circuits to be considered.

Our work evaluates this behavior using combined full-wave and circuit-level analysis. Both **near-field sources and far-field illumination** are considered so that localized coupling mechanisms and system-level exposure can be studied within the same framework. The vulnerability study uses frequency-domain EM analysis, adaptive broadband reduction, and time-domain circuit simulation to connect external EM disturbances to responses at individual IC ports. 

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/emc/emc_ic_vul.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Computational and experimental framework for EM vulnerability analysis of PCB and IC systems.
</div>

Measurements and simulations are then compared across frequency, incident direction, source configuration, and circuit ports. These results help identify **susceptible frequencies, vulnerable directions, dominant coupling paths, and sensitive circuit locations**, providing a more direct link between the external EM environment and circuit-level response.
The measured and simulated near- and far-field results show that the framework can reproduce the main vulnerability trends of a practical PCB and IC system, while also revealing the importance of accurately modeling external structures such as connectors. 

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/emc/emc_ic_vul_res.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Near- and far-field vulnerability analysis of PCB and IC systems, with simulation and measurement used to characterize frequency-dependent and spatial electromagnetic coupling.
</div>


## Toward System-Level EMC

As electronic platforms become increasingly integrated, EMC problems extend beyond individual PCBs and ICs to interactions among **multiple electronic subsystems, antennas, cables, enclosures, sensors, and surrounding structures**. At this scale, detailed local electronics coexist with electrically large platforms, producing substantial challenges in geometry construction, multiscale discretization, and numerical solution.

Our current research extends the modeling and solver techniques developed for PCB- and IC-level EMC toward **large, complex electronic platforms**, including unmanned aerial vehicles and automotive systems. The objective is to combine detailed local models with scalable domain decomposition and fast solution techniques so that emissions, interference paths, antenna coupling, and system-level electromagnetic interactions can be analyzed within a unified computational framework.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/emc/emc_car.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>

<div class="caption">
    Multiscale modeling toward system-level EMC analysis of complex electronic platforms.
</div>


<br>

### Selected Projects & Collaborations

- CERN BCM & Calypso — electromagnetic modeling, simulation, and measurement under the [CYAN Research Program](https://cyan.engineering.osu.edu/) -- was conducted in collaboration with Prof. Jin-Fa Lee, Prof. Kubilay Sertel, and Dr. Shane Smith at The Ohio State University.

--

## Related Research

- [Domain Decomposition Methods](/projects/ddm/)
- [Robust Direct Solvers](/projects/direct_solver/)
- [Coupled-Physics Algorithms](/projects/mphy/)
- [Multiscale Electronics Modeling](/projects/ic/)

--