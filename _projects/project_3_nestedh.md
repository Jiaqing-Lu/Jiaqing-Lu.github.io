---
layout: page
title: Robust Direct Solvers
description: sparse factorization, skeletonization, and low-rank compression
img: assets/img/7.jpg
importance: 3
category: algorithm
research_id: nestedh
permalink: /projects/direct_solver/
related_publications: true
---

Direct solvers provide **reusable factorizations of large numerical systems**, making them particularly attractive for ill-conditioned problems and simulations involving many right-hand sides. Their major limitation, however, is the rapidly increasing computational and memory cost during matrix factorization, and morever, fill-ins for sparse matrices.

Our research develops **structure-aware direct solvers for finite-element and domain-decomposition systems**. By combining nested dissection, skeletonization, hierarchical matrices, and randomized low-rank compression, we reduce large volume systems into multilevel surface representations and perform numerical factorization directly on these compressed structures.

## FEM Direct Solver -- From Volume to Skeletons

Conventional sparse direct solvers factorize the entire finite-element system, even when only a small portion of the solution, such as fields on boundaries or ports, is ultimately required. Our approach instead constructs a direct solver specifically around these engineering-critical regions.

A finite-element mesh is first recursively partitioned using **nested dissection**, producing multilevel subblocks. Starting from the finest-level subblocks, interior degrees of freedom are eliminated and neighboring subblocks are progressively merged in a bottom-up process. This generates a hierarchy of lower-dimensional **skeletons**, eventually condensing the original three-dimensional volume problem onto its boundary.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/nestedh/nestedh_femsolver.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Hierarchical FEM skeletonization: a volume mesh is recursively partitioned and condensed into multilevel surface skeletons and a compressed boundary operator.
</div>

## Hierarchical Low-Rank Compression

Eliminating interior unknowns produces dense interactions among the remaining skeleton degrees of freedom. Rather than storing and manipulating these matrices explicitly, we exploit their **hierarchical low-rank structure**.

Skeleton matrices are organized according to the geometric partition tree and represented using hierarchical matrix formats such as HODLR. Their off-diagonal interactions are compressed through randomized low-rank approximations, avoiding the explicit construction of many dense matrix blocks. Matrix elimination, merging, inversion, and recompression are subsequently performed directly on these compressed representations.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/nestedh/nestedh_compression.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Demonstration of rank structured matrices constructed during FEM skeletonization and factorization.
</div>


For three-dimensional problems of moderate electrical size, the numerical experiments show approximately

- **Memory:** $O(N \log N)$
- **Factorization:** $O(N^{4/3} \log N)$
- **Solution:** $O(N \log N)$

The reduced memory cost and fast solution stage make the approach particularly attractive when the same factorization is reused for many excitations.

## Direct Factorization of Domain Decomposition Systems

The FEM skeleton solver naturally provides a compressed boundary operator for each subdomain. These operators can be assembled into a global domain decomposition system involving only the subdomain interfaces. Instead of solving this system through conventional global iterations, we further construct a **direct factorization of the complete DDM interface system**.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/nestedh/nestedh_ddmsolver.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    From FEM subdomain skeletons to direct factorization of the global DDM interface system.
</div>

The DDM interface system is factorized through a second hierarchical process. Neighboring subdomain skeletons are recursively grouped, reordered into interior and exterior interface variables, and factorized using block LDU operations. Interior interfaces are eliminated while exterior skeletons are retained for subsequent merging. Repeating this process across multiple levels produces a global direct factorization of the DDM system.

This provides an alternative solution path for DDM systems where iterative convergence becomes slow or unreliable, and is especially advantageous when many ports, incident fields, or other right-hand sides must be analyzed using the same computational model.

## Representative Applications

The direct-solver framework has been applied to multiscale and multiport electromagnetic systems. Its advantages become particularly significant when subdomain factorizations can be reused in perodic structures, when many right-hand sides are required, or when conventional DDM iterations converge slowly.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/nestedh/nestedh_antenna.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/nestedh/nestedh_pcb.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Representative applications of the FEM and DDM direct solvers.
</div>

--
### Selected Projects & Collaborations

- *State Key Laboratory of Radio-Frequency Heterogeneous Integration*  
  **Efficient Solvers for Large-Scale Multiphysics Domain Decomposition Systems**, 2026–2028, PI.

- Advanced Direct Solver for FEM and DDM — collaborative research with *Ansys, Inc.* 

--

## Related Research

- [Domain Decomposition Methods](/projects/ddm/)
- [Multiscale Electronics Modeling](/projects/ic/)
- [Antenna & Material Modeling](/projects/ap/)

--