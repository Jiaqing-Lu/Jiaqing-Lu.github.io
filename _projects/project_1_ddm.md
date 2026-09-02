---
layout: page
title: Domain Decomposition Methods
description: nonconformal, embedded, and overlapping formulations
img: assets/img/12.jpg
importance: 1
category: algorithm
research_id: ddm
permalink: /projects/ddm/
related_publications: true
---

**Domain decomposition methods (DDMs)** partition a large problem into smaller subdomains that can be modeled and solved individually and coupled through transmission conditions. They provide a natural framework for large-scale numerical simulations, parallel computing, heterogeneous discretizations, and modular numerical modeling. Our research focuses on **nonconformal and embedded DDM** formulations. In addition to reducing computational complexity, these methods aim to improve the flexibility of the entire simulation workflow by allowing different parts of a system to be modeled, meshed, modified, and reused independently.


## Nonoverlapping and Nonconformal DDM

Nonconformal DDM removes the requirement that neighboring subdomains share matching interface meshes. **Each region can therefore be meshed independently**, allowing different mesh densities and local discretization strategies to be used without constructing a globally conformal mesh.

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
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>


## Embedded/Overlapping DDM

Nonconformal DDM allows neighboring regions to use independent meshes, but the subdomains still form a nonoverlapping partition of the original geometry. Embedded DDM further relaxes this restriction by allowing independently constructed subdomains to overlap geometrically.

A complex system is represented by a background domain together with one or more embedded component domains. Each component can be modeled and meshed independently and then inserted into the background model. Coupling operators are introduced to recover the electromagnetic interactions between the overlapping domains.

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

nonconformal DDM relaxes mesh conformity, whereas Embedded DDM relaxes the geometric decomposition itself.

### Independent Modeling and Meshing
Background and embedded components are constructed independently, allowing different mesh densities, mesh types, and discretization settings to be used for different parts of a multiscale system.

### Physics-Based Coupling
The independently discretized domains are coupled through equivalent surface and volume sources that enforce field continuity, material changes, and embedded boundary conditions such as PEC, impedance boundaries, and ports.

### Reusable Numerical Models
When an embedded component is moved, modified, or replaced, the surrounding background mesh and matrix can remain unchanged. Existing subdomain meshes and matrices can therefore be reused across design iterations and system configurations.

## Representative Applications

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

Embedded DDM has been applied to antenna structures, electronic packaging and interconnects, and large multiscale electromagnetic systems where independent component modeling and repeated design changes are important.


## Selected Projects & Collaborations

- *National Natural Science Foundation of China*  
  **Embedded Domain Decomposition Method for Multiscale Electromagnetic Systems**, 2027–2030, PI.

- Advanced CEM Algorithms for Signal Integrity Analyses in ICs and Packages -- collaborative research with *Ansys, Inc.* 

--

## Related Research

- [Iterative Solvers & Preconditioning](/projects/precond/)
- [Robust Direct Solvers](/projects/nestedh/)
- [Multiscale Electronics Modeling](/projects/ic/)

--