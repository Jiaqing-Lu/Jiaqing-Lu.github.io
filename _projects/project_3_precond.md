---
layout: page
title: Iterative Solvers & Preconditioning
description: scalable iterative methods for large-scale numerical systems
img: assets/img/projects/ddm/embed_ddm.png
importance: 2
category: algorithm
research_id: precond
permalink: /projects/precond/
related_publications: true
---

Iterative solvers are essential for large-scale electromagnetic simulations, but their performance depends strongly on the spectral properties and conditioning of the discretized system. 
Our research focuses on improving the robustness and convergence of iterative electromagnetic solvers through **physics-aware constraints, spectral analysis, and low-rank preconditioning techniques**.

## Iterative Convergence of Domain Decomposition Methods

Domain decomposition methods (DDMs) provide a powerful framework for discretizing complex electromagnetic problems. However, DDMs are intrinsically iterative, and **rapid convergence is not guaranteed even with optimized transmission conditions. Many real-world applications may still require a large number of iterations or even encounter convergence failure.**
For example, highly heterogeneous and multiscale discretizations may lead to ill-conditioned systems, while wave propagation parallel to subdomain interfaces can result in convergence factors approaching unity. 

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/nestedh/precond_pcb.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Representative domain decomposition system with convergence problem and our proposed improvements.
</div>

## Randomized Low-Rank Preconditioning

To improve the robustness of iterative solutions, we construct preconditioners based on an **approximate inverse of the global system matrix**. Rather than explicitly forming and factorizing the complete system matrix, our approach exploits the block structure of the system and approximates the dominant interactions between matrix blocks.

The coupling operators are probed using random vectors, and **randomized sampling is used to extract their dominant low-rank subspaces** without explicitly constructing or factorizing the dense coupling matrices. The resulting low-rank approximations are hierarchically assembled with the local matrix inverses, providing an efficient approximation to the inverse of the complete system.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/nestedh/precond_randomized_sampling.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Randomized low-rank construction of approximate-inverse preconditioners.
</div>

## Preconditioning for Nonoverlapping, Embedded and Hybrid DDM Systems

The preconditioning approach is applyed to conventional nonoverlapping DDM as well as embedded DDM. Its effectiveness can be understood through the eigenspectrum of the iterative system. As the rank of randomized approximation increases, the system's eigenvalues become progressively clustered. We therefore start the preconditioner with a small rank and increase the rank adaptively, meanwhile estimate the spectral radius of system. In this way, a stronger preconditioner is constructed only when it is actually needed.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/nestedh/precond_embed_ddm.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Application of the preconditioning framework to embedded domain decomposition systems, with the reduction of spectral radius and iteration number as dominant coupling information is progressively incorporated into the preconditioner.
</div>

More complex systems can contain **both embedded and nonoverlapping subdomain couplings**. For example, independently modeled components may be embedded within a background domain, while neighboring embedded components are connected through conventional touching interfaces. The same framework can incorporate both types of interactions and precondition the resulting hybrid system. 

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/nestedh/precond_hybrid_ddm.png"
            class="img-fluid rounded z-depth-0" 
            avoid_scaling=true
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Application of the preconditioning framework to a hybrid domain decomposition system.
</div>

<br>

### Selected Projects & Collaborations
- *Ansys, Inc.*  
  **Advanced Computational HF Techniques**, 2016–2023, Primary contributor.  

--

## Related Research

- [Domain Decomposition Methods](/projects/ddm/)
- [Multiscale Electronics Modeling](/projects/ic/)
- [Antenna & Material Modeling](/projects/ap/)

--