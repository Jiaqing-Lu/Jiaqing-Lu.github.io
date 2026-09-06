---
layout: page
title: Coupled-Physics Algorithms
description: coupled electromagnetic, circuit, and thermal computation
img: assets/img/4.jpg
importance: 5
category: algorithm
research_id: mphy
related_publications: true
permalink: /projects/mphy/
---

Modern electromagnetic (EM) systems increasingly involve interactions among **EM fields, circuits, semiconductor devices, and thermal processes**. These components are often governed by different physical models, numerical discretizations, spatial and temporal scales, and simulation environments. 
Rather than force different physical subsystems into a single monolithic formulation, our research explores **nonconformal coupled-physics frameworks**, as a conceptual extension of nonconformal domain decomposition, where individual subsystems should use numerical models and solution strategies appropriate to their own characteristics.

Our current research focuses on **EM–circuit coupling** and its extension toward **EM–thermal computation**. Particular attention is given to numerical interfaces between independently developed solvers, efficient information exchange across physical domains, and the integration of full-wave EM simulation with established engineering models and software.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/mphy/mphy_emckt.png"
            class="img-fluid rounded z-depth-0" 
            <!-- avoid_scaling=true -->
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Coupled EM–circuit simulation frameworks in the time and frequency domains.
</div>

## Time-Domain EM–Circuit Coupling

Our first approach performs EM and circuit computations **jointly in the time domain**, allowing nonlinear circuit behavior to interact directly with
transient full-wave EM fields.
Surface ports provide the interfaces between the EM and circuit subsystems. At each coupling step, EM field quantities are converted into port voltages and currents, while the circuit responses are returned to the EM solver through surface currents. **Effectively, the circuits are incorporated into transient full-wave simulation as nonlinear impedance surfaces**. 

The time-domain co-simulation is suitable when the complexity and nonlinearity of circuit models can be efficiently addressed at each time step, allowing the circuit and EM computations to proceed in parallel.
However, frequent information exchange between independently implemented solvers can introduce additional computational and communication costs.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/mphy/mphy_emckt_td.png"
            class="img-fluid rounded z-depth-0" 
            <!-- avoid_scaling=true -->
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Representative applications of transient EM-circuit co-simulation.
</div>

## Mixed-Domain EM–Circuit Coupling

For complex electronic systems, we further developed a **mixed-domain co-simulation framework** that combines frequency-domain EM analysis with time-domain circuit simulation.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/mphy/mphy_emckt_fd.png"
            class="img-fluid rounded z-depth-0" 
            <!-- avoid_scaling=true -->
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Mixed domain EM-circuit co-simulation with domain decomposition, adaptive rational interpolation, and model-order reduction.
</div>

The electromagnetic subsystem is treated as a linear multiport system and analyzed using FEM and nonconformal domain decomposition. Its broadband response is constructed through an **adaptive frequency sweep**, where a Loewner-matrix-based rational approximation guides the selection of additional full-wave frequency samples until desired accuracy is reached. The resulting frequency-dependent scattering matrix provides a reduced-order EM representation and can be directly integrated into established circuit simulation environments for nonlinear and mixed-signal analysis. This enables established circuit solvers, semiconductor libraries, and commercial device models to be used without reproducing their functionality within the EM program. After circuit simulation, the port responses can be mapped back to the full-wave EM model to reconstruct the corresponding electromagnetic fields and currents.

For large electronic systems, we further employ **hierarchical Schur-complement compression** to reduce the spatial EM system while retaining detailed field information in critical regions. Combined with adaptive frequency sweeping, these techniques provide a **frequency–spatial model-order-reduction framework for coupled EM–circuit simulations**.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/mphy/mphy_emckt_bcm.png"
            class="img-fluid rounded z-depth-0" 
            <!-- avoid_scaling=true -->
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Representative application of mixed-domain EM-circuit co-simulation.
</div>

See [EMC/EMI & Side-Channel Analysis](/projects/emc/) for detailed applications and experimental validation.


## Ongoing Research

Our current research extends the coupled-physics framework toward **electromagnetic–thermal analysis** of large-scale electronic systems.
Electromagnetic power losses provide heat sources for thermal computation, while temperature-dependent material and device properties can in turn
modify electromagnetic behavior. 

Current work focuses on numerical coupling between independently discretized electromagnetic and thermal models, together with scalable direct/iterative solution
strategies for large coupled systems. These developments aim toward a unified computational framework for electromagnetic, circuit, and thermal analysis.



<br>

## Selected Projects & Collaborations

- *State Key Laboratory of Radio-Frequency Heterogeneous Integration*  
  **Efficient Solvers for Large-Scale Multiphysics Domain Decomposition Systems**, 2026–2028, PI.

- **Brave Heart** project — electromagnetic-circuit co-simulation package for circuit boards — with *DSO National Laboratories, Singapore*.

--

## Related Research

- [Domain Decomposition Methods](/projects/ddm/)
- [Iterative Solvers & Preconditioning](/projects/precond/)
- [Robust Direct Solvers](/projects/direct_solver/)
- [Discontinuous Galerkin Methods](/projects/dg/)
- [Multiscale Electronics Modeling](/projects/ic/)

--