---
layout: page
title: Domain Decomposition Methods
description: nonconformal, embedded, and overlapping formulations
img: assets/img/projects/project_embed_ddm.png
importance: 1
category: algorithm
research_id: ddm
permalink: /projects/ddm/
related_publications: true
---

**Domain decomposition methods (DDMs)** partition a large problem into smaller subdomains that can be modeled and solved individually and coupled through transmission conditions. They provide a natural framework for large-scale numerical simulations, parallel computing, heterogeneous discretizations, and modular numerical modeling. 

As EM systems become increasingly complex, modeling and meshing are taking an increasingly large portion of the overall simulation effort. **The challenge is not only how to solve a large problem efficiently, but also how to model it efficiently, and how to reuse what has already been computed**.
Our research focuses on **nonconformal and embedded domain decomposition formulations**. In addition to reducing computational complexity, we aim to improve the flexibility of the entire simulation workflow by allowing different parts of a system to be modeled, meshed, modified, and reused effectively.

<div class="row align-items-center">
    <div class="col-sm-8 mt-3 mt-md-0"> 
        {% include figure.liquid 
            path="assets/img/projects/ddm/ddm_conformal_1.png"
            class="img-fluid rounded z-depth-0" 
            height="250px"
        %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/ddm/ddm_conformal_2.png"
            class="img-fluid rounded z-depth-0" 
            height="250px"
        %}
    </div>
</div>
<div class="caption">
  Illustration of DDM and conformal mesh partitioning.
</div>


## Nonoverlapping and Nonconformal DDMs

Nonconformal DDMs remove the requirement that neighboring subdomains share matching interface meshes. Compared to conformal DDMs, **each subdomain can be meshed independently**, allowing different mesh densities and local discretization strategies to be used without constructing a globally conformal mesh.

<div class="row align-items-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/ddm/ddm_nonconformal_1.png"
            class="img-fluid rounded z-depth-0" 
            max-height="250px"
        %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/ddm/ddm_nonconformal_2.png"
            class="img-fluid rounded z-depth-0" 
            max-height="250px"
        %}
    </div>
    <div class="col-sm-3 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/ddm/ddm_nonconformal_3.png"
            class="img-fluid rounded z-depth-0" 
            max-height="250px"
        %}
    </div>
</div>
<div class="caption">
    Illustration of nonconformal DDMs with independently generated, nonmatching meshes across neighboring subdomains.
</div>


## Embedded/Overlapping DDM

Nonconformal DDM allows neighboring regions to use independent meshes, but the subdomain interfaces remain geometrically conformal, i.e., forming a nonoverlapping partition of the original geometry. Embedded DDM further relaxes this restriction by allowing independently constructed subdomains to overlap in geometries and meshes. Nonconformal DDM relaxes mesh conformity, whereas Embedded DDM relaxes both geometric and mesh complexities.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/ddm/embed_ddm_overview.png"
            class="img-fluid rounded z-depth-0" 
        %}
    </div>
</div>
<div class="caption">
    Demonstration of embedded DDM, where subdomains are geometrically nonconformal and computationally independent.
</div>

A complex system is represented by multiple component subdomains. Each component can be modeled and meshed independently, enabling a flexible framework for modular and multiscale electromagnetic modeling:

- **Independent Modeling and Meshing**: background and embedded components are constructed independently, allowing different mesh densities, mesh types, and discretization settings to coexist across different parts of a multiscale system.

- **Physics-Based Coupling**: the independently discretized domains are coupled through equivalent surface and volume sources that enforce field continuity, material difference, and embedded boundary conditions such as PEC, impedance boundaries, and ports.

- **Reusable Numerical Models**: when an embedded component is moved, modified, or replaced, the meshes and matrices of existing subdomains remain unchanged. Constructed subdomain meshes and matrices can therefore be reused across design iterations and system configurations.


## Representative Applications
Embedded DDM has been applied to antenna structures, electronic packaging and interconnects, and multiscale electromagnetic systems where flexible component modeling and repeated design explorations are important.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/ddm/embed_ddm_headcellphone.png"
            class="img-fluid rounded z-depth-0" 
        %}
    </div>
</div>
<div class="caption">
    Application example of embedded DDM: predicting cellphone performance for different hand gestures and positions with one set of meshes.
</div>


## Selected Projects & Collaborations

- *National Natural Science Foundation of China*  
  **Embedded Domain Decomposition Method for Multiscale Electromagnetic Systems**, 2027–2030, PI.

- Advanced CEM Algorithms for Signal Integrity Analyses in ICs and Packages -- collaborative research with *Ansys, Inc.* 

--

## Related Research

- [Iterative Solvers & Preconditioning](/projects/precond/)
- [Robust Direct Solvers](/projects/direct_solver/)
- [Multiscale Electronics Modeling](/projects/ic/)

--