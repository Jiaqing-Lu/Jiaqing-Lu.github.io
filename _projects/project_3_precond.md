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

Domain decomposition methods (DDMs) provide a powerful framework for discretizing complex electromagnetic problems. However, DDMs are intrinsically iterative solvers. **Rapid convergence is not guaranteed even with optimized transmission conditions, and many real-world applications still require a large number of iterations, or lead to convergence failure.**
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
  Representative domain decomposition system with convergence problem and the effects of our proposed improvements.
</div>

## Randomized Low-Rank Preconditioning

To improve the robustness of iterations, we construct preconditioners based on an **approximate inverse of the global system matrix**. Our approach employs randomized samples to identify the dominant global interaction modes, so as to avoid entrywise matrix factorizations.

To form the preconditioner, we utilize the matrix that represent the coupling of matrix blocks. Instead of explicitly constructing the dense coupling operator, we probe it using random vectors and **use randomized sampling to extract its dominant low-rank subspace**. The resulting low-rank approximations are hierarchically assembled, providing an efficient approximation to the inverse of the complete system matrix.

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

## Nonoverlapping, Embedded and Hybrid Domain Decomposition

The preconditioning approach is applyed to conventional nonoverlapping DDM as well as embedded DDM. The effectiveness of a preconditioner can be understood through its influence on the eigenspectrum of the iterative system. As we increase the rank of the randomized preconditioner, the eigenvalues become progressively clustered. We therefore start with a small rank and increase it adaptively, meanwhile estimate the spectral radius of system. In this way, we use a stronger preconditioner only when it is actually needed.

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
    Application of the preconditioning framework to embedded domain decomposition systems, with the reduction of spectral radius and iterative number as dominant coupling information is progressively incorporated into the preconditioner.
</div>

More complex systems can contain **both embedded and nonoverlapping subdomain couplings**. For example, independently modeled components may be embedded within a background domain while neighboring embedded components are connected through conventional touching interfaces. The same framework can incorporate both types of interactions and precondition the resulting hybrid system. 

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
    Application of the preconditioning framework to hybrid domain decomposition systems.
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