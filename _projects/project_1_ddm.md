---
layout: page
title: Domain Decomposition Methods
description: nonconformal, embedded, and overlapping formulations
img: assets/img/projects/ddm/ddm_overview.png
importance: 1
category: algorithm
research_id: ddm
permalink: /projects/ddm/
related_publications: true
---

**Domain decomposition methods (DDMs)** partition a large problem into smaller subdomains that can be modeled and solved individually and coupled through transmission conditions. They provide a natural framework for large-scale numerical simulations, parallel computing, heterogeneous discretizations, and modular numerical modeling. 

As EM systems become increasingly complicated, modeling and meshing are taking an increasingly large portion of the overall simulation effort. **The question is not only how to solve a large problem efficiently, but also how to model it efficiently, and how to reuse what has already been computed**.
Our research focuses on **nonconformal and embedded domain decomposition formulations**. In addition to reducing computational complexity, we aim to improve the flexibility of the entire simulation workflow by allowing different parts of a system to be modeled, meshed, modified, and reused effectively.


## Nonoverlapping and Nonconformal DDMs

Nonconformal DDMs remove the requirement that neighboring subdomains share matching interface meshes. Compared to conformal DDMs, **Each region can be meshed independently**, allowing different mesh densities and local discretization strategies to be used without constructing a globally conformal mesh.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Illustration of conformal DDMs.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Illustration of nonconformal DDMs, where nonmatching grids can coexist at neighboring subdomains.
</div>


## Embedded/Overlapping DDM

Nonconformal DDM allows neighboring regions to use independent meshes, but the subdomain boundaries remain geometrically conformal, i.e., forming a nonoverlapping partition of the original geometry. Embedded DDM further relaxes this restriction by allowing independently constructed subdomains to overlap in geometries and meshes. Nonconformal DDM relaxes mesh conformity, whereas Embedded DDM relaxes both geometric and mesh complexities.

A complex system is represented by multiple component subdomains. Each component can be modeled and meshed independently, enabling a more flexible system-level modeling framework:

- **Independent Modeling and Meshing**: background and embedded components are constructed independently, allowing different mesh densities, mesh types, and discretization settings to be used for different parts of a multiscale system.

- **Physics-Based Coupling**: the independently discretized domains are coupled through equivalent surface and volume sources that enforce field continuity, material changes, and embedded boundary conditions such as PEC, impedance boundaries, and ports.

- **Reusable Numerical Models**: when an embedded component is moved, modified, or replaced, the mesh and matrix of existing subdomains remain unchanged. Constructed subdomain meshes and matrices can therefore be reused across design iterations and system configurations.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>



## Representative Applications
Embedded DDM has been applied to antenna structures, electronic packaging and interconnects, and multiscale electromagnetic systems where flexible component modeling and repeated design explorations are important.

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}


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