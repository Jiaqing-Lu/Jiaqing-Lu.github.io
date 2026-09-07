---
layout: page
title: Multiscale Electronics Modeling
description: IC, package, PCB, and system-level multiscale modeling 
img: assets/img/projects/project_ic.png
importance: 1
category: application
research_id: ic
permalink: /projects/ic/
related_publications: true
---

Modern electronic systems integrate ICs, packages, interconnects, multilayer PCBs, and mounted components across widely different geometrical scales. Their electromagnetic simulation is challenging not only because of the resulting problem size, but also because **different parts of the system have very different geometrical features, discretization requirements, and levels of modeling details**.

Our research addresses these challenges through a combination of **nonconformal and embedded domain decomposition, hierarchical direct and iterative solvers, and reduced-order techniques**. The emphasis is on developing flexible and scalable computational frameworks for realistic electronic systems, from detailed component modeling to system-level electromagnetic analysis.

## Complex Multilayered Structures

Electronic systems naturally contain multiple conducting and dielectric layers, traces, vias, packages, ports, and mounted components. Constructing and maintaining a single globally conformal discretization becomes increasingly difficult as the geometrical complexity grows.

We employ [nonconformal domain decomposition method](/projects/ddm/) to separate complex electronic structures into independently constructed computational regions. For multilayer circuits, individual layers can be generated directly from their design data and further partitioned into smaller building blocks. Each subdomain can then be meshed independently, while electromagnetic interactions between neighboring regions are enforced through nonconformal interfaces.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/ic/ic_pcb_model.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    From layered PCB design data to independently constructed subdomains for nonconformal electromagnetic simulation.
</div>

Such a decomposition scheme provides considerable efficiency for practical PCB modeling. Different layers and local regions can employ mesh resolutions appropriate to their geometrical features.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/ic/ic_pcb_eg.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Nonconformal decomposition of a multilayer PCB into independently meshed layers and subdomains for large-scale multiport simulation.
</div>


## Multiscale Modeling & Design Iterations

The modeling difficulty becomes greater when electronic systems contain strongly multiscale components. Fine IC/package features may coexist with much larger substrates, interconnects, and surrounding structures, while repeated design modifications may affect only a small portion of the complete model.

Our [embedded domain decomposition method](/projects/ddm/) is suitable to handle such problems. Selected components can be modeled with independent geometries and meshes and subsequently embedded into larger computational domains. Components can consequently be refined, replaced, or modified without rebuilding the complete surrounding discretization.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/ic/ic_embed_ddm.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>

<div class="caption">
    Multiscale PCB, package, and interconnect modeling using embedded domain decomposition, allowing independently constructed component and system models to be integrated within the same simulation.
</div>

This modular treatment is particularly useful for **design iterations**, where local components may undergo repeated changes while most of the surrounding computational models and matrices remain unchanged. It also provides a natural framework for combining different levels of geometrical detail within a system-level simulation.


## Scalable Solution of Large Electronic Systems

Flexible multiscale modeling does not by itself remove the computational difficulty of the resulting numerical systems. Practical electronic models may contain millions of unknowns, many ports and excitations, repeated analyses, and domain-decomposition systems whose iterative convergence can become slow or unreliable.

Our [iterative solvers and preconditioning](/projects/precond/) and [hierarchical direct solvers](/projects/direct_solver/) provide robust solution strategies for these large systems. In particular, hierarchical skeletonization and low-rank compression reduce the computational and memory requirements of direct factorization, while reusable subdomain factorizations are well suited to repeated and multiport simulations.

For complete electronic systems, accurate radiation and EMC analysis requires the modeling framework and numerical solver to work together. We integrate [higher-order boundary treatments](/projects/datai/), subdomain skeletonization, and [hierarchical direct solution](/projects/direct_solver/) within the DDM framework. This allows the computational domain to be more tightly bounded while maintaining accurate exterior-field truncation, and provides robust and efficient solutions for large multiscale systems with many excitations. In practical electronic-device simulations, the resulting framework achieves radiation predictions approaching those obtained with integral-equation-based truncation, but with substantially reduced computational cost.


<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/ic/ic_cellphone.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>

<div class="caption">
    System-level electromagnetic simulation of a mobile device integrating multiscale domain decomposition, hierarchical direct solution, and improved electromagnetic truncation.
<
</div>

Together, these techniques connect **flexible geometry construction, multiscale decomposition, and scalable numerical solution** within a unified framework for electromagnetic modeling of complex electronic systems.


<br>

## Selected Projects & Collaborations

- *National Natural Science Foundation of China*  
  **Embedded Domain Decomposition Method for Multiscale Electromagnetic Systems**, 2027–2030, PI.

- **Brave Heart** project — electromagnetic-circuit co-simulation package for circuit boards — with *DSO National Laboratories, Singapore*.

--

## Related Research

- [Domain Decomposition Methods](/projects/ddm/)
- [Iterative Solvers & Preconditioning](/projects/precond/)
- [Robust Direct Solvers](/projects/direct_solver/)
- [Coupled-Physics Algorithms](/projects/mphy/)
- [Scientific Data Learning](/projects/datai/)

--
