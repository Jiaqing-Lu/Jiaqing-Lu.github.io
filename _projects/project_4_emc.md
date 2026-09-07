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

Electromagnetic compatibility (EMC) becomes increasingly difficult to assess as electronic systems integrate dense PCBs, packages, ICs, antennas, interconnects, and nonlinear circuit components within a common electromagnetic environment. Unintended electromagnetic coupling can occur across multiple physical scales and through both conducted and radiated paths, making system-level prediction considerably more challenging than the characterization of individual components.

Our research develops **full-wave computational and experimental approaches for analyzing electromagnetic emissions, interference, and vulnerability of complex electronic systems**. We combine electromagnetic modeling, circuit analysis, and measurements to characterize how electromagnetic energy is generated, coupled, radiated, and received throughout an electronic system.

The underlying numerical framework draws upon our work on [domain decomposition methods](/projects/ddm/), [multiscale electronics modeling](/projects/ic/), [hierarchical direct solvers](/projects/direct_solver/), and [EM-circuit co-simulation](/projects/mphy/), allowing detailed device structures and their surrounding electromagnetic environment to be considered within a common analysis.

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
    Computational and experimental characterization of electromagnetic interactions in PCB and IC systems, combining full-wave simulation, circuit modeling, and RF/microwave measurements.
</div>


## Electromagnetic Emissions

Unintended electromagnetic emissions from electronic circuits provide an important measure of EMC performance. Modern PCBs and ICs contain complicated multilayer geometries, discontinuous ground structures, dense interconnects, and numerous excitation sources. Their near-field radiation can therefore be difficult to characterize accurately using simplified equivalent-source models alone.

We employ full-wave simulations together with near-field measurements to directly characterize these emissions. Detailed PCB geometries are represented using [domain decomposition methods](/projects/ddm/), while measurement configurations—including the field probe and its interaction with the device under test—can be incorporated into the computational model. This provides a common basis for comparing simulated and measured field distributions and for identifying electromagnetic hot spots and dominant radiation regions.

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
    Near-field electromagnetic-emission measurement and full-wave modeling of practical PCB and IC systems.
</div>

For systems containing active and nonlinear devices, electromagnetic radiation cannot be determined from the passive PCB structure alone. We further integrate full-wave electromagnetic analysis with circuit models through [EM-circuit co-simulation](/projects/mphy/), allowing circuit responses to provide realistic excitations for subsequent field reconstruction and emission analysis.

Combined with [hierarchical direct solution](/projects/direct_solver/), model reduction, and efficient treatment of multiple excitations, this framework enables electromagnetic emissions from increasingly complex RF and mixed-signal electronic systems to be evaluated over broad frequency ranges.

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
    Simulation and measurement of near-field emissions, including field distributions, emission hot spots, and the influence of practical measurement probes.
</div>


## Electromagnetic Interference & Vulnerability

The complementary EMC problem concerns how electronic systems respond to **external electromagnetic interference (EMI)**. Incident fields may couple through PCB traces, interconnects, connectors, packages, and other structures before reaching sensitive circuit components. Accurate vulnerability assessment therefore requires both the propagation of electromagnetic fields through the physical system and the resulting electrical responses of the circuits to be considered.

Our [EM-circuit co-simulation framework](/projects/mphy/) separates the problem into a full-wave electromagnetic subsystem and a circuit subsystem. Broadband electromagnetic responses are obtained from frequency-domain simulations and efficiently represented through adaptive model reduction, while established circuit solvers handle nonlinear and mixed-signal device behavior. This enables detailed IC models to be retained without sacrificing the flexibility of full-wave electromagnetic modeling.

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
    EM-circuit co-simulation and experimental characterization for assessing the response of PCB and IC systems to external electromagnetic interference.
</div>

Both **near-field and far-field interference** are considered. Near-field sources allow localized coupling paths and sensitive regions to be investigated, while controlled far-field illumination provides a system-level assessment under incident electromagnetic waves. Comparisons between simulations and measurements are used to identify vulnerable frequencies, directions, coupling paths, and circuit responses.

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

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/emc/emc_car.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>

<div class="caption">
    Extension of multiscale electromagnetic modeling toward system-level EMC analysis of complex electronic platforms.
</div>


<br>

### Selected Projects & Collaborations

- CERN BCM & Calypso — electromagnetic modeling, simulation, and measurement with [CYAN Research Program, OSU](https://cyan.engineering.osu.edu/) -- conducted in collaboration with Prof. Jin-Fa Lee, Prof. Kubilay Sertel, and Dr. Shane Smith at The Ohio State University.

--