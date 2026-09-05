---
layout: page
title: Discontinuous Galerkin Methods
description: space-time solution strategies
img: assets/img/3.jpg
importance: 4
category: algorithm
research_id: dg
permalink: /projects/dg/
related_publications: true
# giscus_comments: true
---

**Discontinuous Galerkin (DG) methods** combine element-local discretizations with interface-based numerical coupling, providing a flexible framework between conventional finite/boundary element and domain decomposition methods. By allowing the approximation spaces to remain discontinuous across element boundaries, DG methods support local discretizations, nonconformal meshes, explicit time marching, and highly parallel computation.

Our research explores DG methods as a framework for local and multiscale numerical modeling, multiphysics coupling, and space-time computation.

## Interior-Penalty DG for Electromagnetics

Our DG research builds upon the **interior-penalty discontinuous Galerkin time-domain (IP-DGTD)** method developed in Prof. Jin-Fa Lee's group at The Ohio State University. In this formulation, electromagnetic fields are represented independently within individual elements, while physical continuity conditions are weakly enforced at element interfaces through interior-penalty formulation.

This element-local structure provides considerable flexibility for electromagnetic computation. Different regions can employ independent discretizations, while local time stepping can alleviate the restrictive global time-step requirement introduced by small or highly refined elements.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/dg/dg_ipdg.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Element-local discretization and interface coupling in discontinuous Galerkin methods.
</div>

### Foundational Work

- S. Dosopoulos and J.-F. Lee, Interior Penalty Discontinuous Galerkin Finite Element Method for the Time-Dependent First Order Maxwell's Equations, *IEEE Transactions on Antennas and Propagation*, Dec 2010.
- S. Dosopoulos and J.-F. Lee, Non-conformal and Parallel Discontinuous Galerkin Time Domain Method for Maxwell's Equations: EM Analysis of IC Packages, *Journal of Computational Physics*, Dec 2012.

<br>

## DG-Based EM–Circuit Coupling

The interface-based structure of DG also provides a natural mechanism for coupling electromagnetic fields with external circuit models. Our research extends IP-DGTD from conventional electromagnetic interfaces to EM-circuit coupling, incorporating both SPICE and IBIS models for circuit/device representation. 

The electromagnetic and circuit subsystems are coupled through circuit ports based on the concept of impedance surface. A self-consistent interface procedure exchanges field information between the two systems and enforces their compatibility during time-domain simulation.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm-9 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/dg/dg_emckt.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Illustration of the DG-circuit coupling mechanism.
</div>

## Representative Applications

The DGTD framework has been applied to large-scale electronic systems involving **multilayer PCBs, high-speed interconnects, nonlinear circuit components, and digital I/O models**. These examples demonstrate the combination of nonconformal discretization, parallel domain partitioning, local time stepping, and EM–circuit co-simulation within a unified time-domain framework.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/dg/dg_pcb.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/dg/dg_pcb_results.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Large-scale multilayer PCB modeled using the DGTD, including high-speed interconnects, packaged devices, and circuit components.
</div>

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/dg/dg_pcb_mpi.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Domain and mesh partitions for parallel simulation. Individual PCB layers are meshed nonconformally and further partitioned into subdomains distributed across MPI processes.
</div>


## Ongoing Research

Our current research explores new DG formulations and solution strategies for large-scale transient electromagnetic problems. We are particularly interested in reducing the computational and communication costs associated with conventional element-level DG methods while preserving their locality, flexibility, and compatibility with heterogeneous discretizations.

Related directions include connections with our research on domain decomposition, fast numerical solvers, and multilevel computational methods for large-scale electromagnetic simulation.


<br>

### Selected Projects & Collaborations

- **Brave Heart** project — electromagnetic-circuit co-simulation package for circuit boards — with *DSO National Laboratories, Singapore*.

- Earlier DG research was conducted in collaboration with Dr. Jue Wang and Prof. Jin-Fa Lee at The Ohio State University.

--

## Related Research

- [Coupled-Physics Algorithms](/projects/mphy/)
- [Multiscale Electronics Modeling](/projects/ic/)

--