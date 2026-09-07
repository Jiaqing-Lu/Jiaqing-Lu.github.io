---
layout: page
title: Thermal & Multiphysics
description: electronics heating, high-power EMI
img: assets/img/projects/project_thermal.png
importance: 3
category: application
research_id: thermal
permalink: /projects/thermal/
related_publications: true
---

Thermal effects are intertwined with electrical and electromagnetic (EM) behavior in high-power and highly integrated electronic systems. Joule heating, temperature-dependent material properties, power delivery, EM losses, and environmental conditions can form strongly coupled multiphysics processes across very different spatial and temporal scales.

Our research explores **thermal and multiphysics applications of the computational methods developed throughout our research**, including [domain decomposition methods](/projects/ddm/), [DG methods](/projects/dg/), [scalable iterative solvers](/projects/precond/), and [hierarchical direct solvers](/projects/direct_solver/). These methods provide a flexible numerical foundation for extending large-scale electromagnetic simulation toward coupled electrical, thermal, and other physical effects.

## Steady-State Electrothermal Analysis

Electronic systems naturally involve thermal structures spanning very different scales, from ICs and packages to PCBs, thermal interface materials, heat spreaders, and heat sinks. Their electrical and thermal behaviors are also mutually dependent: electrical power dissipation provides heat sources, while the resulting temperature distribution changes material properties and consequently affects electrical performance.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid
            path="assets/img/projects/thermal/thermal_steady.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Steady-state electrothermal analysis of multiscale electronic systems, coupling electrical power distribution, temperature-dependent material properties, and thermal responses.
</div>

This research direction builds upon the foundational work of Dr. Yang Shao at The Ohio State University on the electrothermal analysis of multiscale chip-package-PCB systems and related domain decomposition applications. 

### Foundational Work

- Y. Shao, Z. Peng, and J.-F. Lee, “Thermal-aware DC IR-drop co-analysis using non-conformal domain decomposition methods,” *Proceedings of the Royal Society A*, Feb 2012.
- Y. Shao, Z. Peng, and J.-F. Lee, “Thermal Analysis of High-Power Integrated Circuits and Packages Using Nonconformal Domain Decomposition Method,” *IEEE Transactions on Components, Packaging and Manufacturing Technology*, Aug 2013.


Building on these foundations, we have been exploring thermal DDM implementations and their integration with our computational frameworks. Current work also includes extending embedded domain decomposition to thermal modeling, together with scalable iterative and direct solution techniques for geometrically intricate systems.

<br>

## Transient EM–Thermal Analysis

Transient multiphysics problems introduce an additional challenge because the characteristic scales may differ substantially **in both space and time**. Fast EM transient bahavior can coexist with much slower thermal evolution, while localized electronic structures may require spatial resolutions very different from those of the surrounding system.

Our work on [discontinuous Galerkin methods](/projects/dg/) provides a natural numerical foundation for such problems. The local character of DG allows different regions to retain independent spatial discretizations. Together with [nonoverlapping and/or embedded DDM](/projects/ddm/), they may constitute a framework for coupling EM and thermal models with different spatial and temporal scales.

The objective is to capture transient multiphysics interactions **without forcing all physical subsystems to adopt the same spatial and temporal resolution**, enabling computational effort to be adapted to the characteristic scales of the underlying physics.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid
            path="assets/img/projects/thermal/thermal_transient.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Transient EM–thermal modeling of electronic systems, coupling electromagnetic power deposition with thermal response across different spatial and temporal scales.
</div>


## High-Power Electromagnetic & Thermal Effects

Beyond conventional electrothermal analysis, our research also extends toward the responses of electronic systems under **high-power electromagnetic pulses (EMP) and other extreme electromagnetic environments**. Sufficiently strong EM excitation can induce substantial currents and localized power deposition, potentially producing heating, changes in material properties, and other nonlinear physical responses.

This direction extends naturally our work on [EM interference and vulnerability](/projects/emc/). Of particular interest is understanding how incident EM energy propagates through complex electronic systems, where it becomes concentrated, and how these localized interactions translate into thermal and physical effects at the device and system levels.
At sufficiently high field strengths, the relevant physics may extend beyond conventional linear EM and thermal models, motivating further investigation of **nonlinear material responses and plasma-related phenomena**.


<br>

## Selected Projects & Collaborations

- *State Key Laboratory of Radio-Frequency Heterogeneous Integration*  
  **Efficient Solvers for Large-Scale Multiphysics Domain Decomposition Systems**, 2026–2028, PI.

- Currently collaborate with Prof. Min Tang at Shanghai Jiao Tong University, on computational thermal and multiphysics modeling.

--

## Related Research

- [Coupled-Physics Algorithms](/projects/mphy/)
- [Electromagnetic Compatibility](/projects/emc/)
- [Domain Decomposition Methods](/projects/ddm/)
- [Multiscale Electronics Modeling](/projects/ic/)

--
