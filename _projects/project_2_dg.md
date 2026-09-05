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

Our DG research builds upon the **interior-penalty discontinuous Galerkin time-domain (IP-DGTD)** method developed in Prof. Jin-Fa Lee's group at The Ohio State University. In this formulation, electromagnetic fields are represented independently within individual elements, while tangential field continuity is weakly enforced through interface conditions across elements.

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

- S. Dosopoulos and J.-F. Lee, Interior Penalty Discontinuous Galerkin Finite Element Method for the Time-Dependent First Order Maxwell's Equations, IEEE TAP, 2010.
- S. Dosopoulos and J.-F. Lee, Non-conformal and Parallel Discontinuous Galerkin Time Domain Method for Maxwell's Equations: EM Analysis of IC Packages, JCP, 2013.


## DG-circuit coupling

The interface-based structure of DG also provides a natural mechanism for coupling electromagnetic fields with other physical or circuit models. Our research extends IP-DGTD from conventional electromagnetic interfaces to EM–circuit coupling. simulation program with integrated circuit emphasis (SPICE) and input/output buffer information specification (IBIS) models are investigated for circuit simulation. 
The electromagnetic and circuit subsystems are coupled through circuit ports based on
the concept of impedance surface, while a self-consistent interface procedure enforces compatibility between the two systems.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
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

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/dg/dg_pcb.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/dg/dg_pcb_results.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    A representative PCB example for DGTD simualtion.
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
    Domain and mesh partitions for parallel simulation. The layers are meshed nonconformally. In each layer, the meshes are further partitioned into smaller subdomains. Each subdomain is mapped to a MPI process.
</div>


## Ongoing Research

Our current research explores new DG formulations and solution strategies for large-scale transient electromagnetic problems. We are particularly interested in reducing the computational and communication costs associated with conventional element-level DG methods while preserving their locality, flexibility, and compatibility with heterogeneous discretizations.

Related directions include the integration of our research on domain decomposition, iterative/direct solvers, and hierarchical low-rank approximation techniques into the IP-DG framework.




<br>

### Selected Projects & Collaborations

- **Brave Heart** project — electromagnetic-circuit co-simulation package for circuit boards — with *DSO National Laboratories, Singapore*.

- Past Collaborator: Jue Wang -- phd thesis ...

--

## Related Research

- [Coupled-Physics Algorithms](/projects/mphy/)
- [Multiscale Electronics Modeling](/projects/ic/)

--