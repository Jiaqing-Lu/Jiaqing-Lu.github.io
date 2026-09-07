---
layout: page
title: Antenna & Material Modeling
description: antenna arrays, frequency selective surfaces, artificial materials
img: assets/img/projects/project_ap.png
importance: 1
category: application
research_id: ap
permalink: /projects/ap/
related_publications: true
# giscus_comments: true
---

Large antenna systems, periodic structures, and engineered electromagnetic surfaces present several common computational challenges. Complex or multiscale components must be incorporated into large platforms, repeated structures should be exploited rather than independently recomputed, and radiation problems require accurate treatment of electrically open domains.

Our research addresses these challenges by combining
[domain decomposition methods](/projects/ddm/),
[iterative and direct solution strategies](/projects/precond/), and
[advanced boundary and material treatments](/projects/datai/).
The objective is to retain the flexibility of full-wave finite-element modeling while exploiting the geometrical and algebraic structures characteristic of practical (semi-)periodic systems.


## Flexible Modeling and Design with DDMs

Antenna design frequently involves localized structures whose geometrical scales and design parameters differ substantially from those of the surrounding array or platform. Requiring all components to share a single conforming discretization can make geometry construction and repeated design modification unnecessarily restrictive.

Our [embedded domain decomposition method](/projects/ddm/) allows antenna elements, feeding structures, and other local components to be modeled and meshed independently from their surrounding domains. Local structures can therefore be modified, replaced, or refined without reconstructing the complete computational model.

This capability is particularly useful for antenna-array design, where a relatively small number of functional or tuning regions may be embedded within a much larger repetitive structure. Independent subdomain models can also incorporate circuit ports and other local representations while retaining full-wave coupling with the surrounding array.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid
            path="assets/img/projects/ap/ap_array_embed_ddm.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Embedded domain decomposition for flexible modeling, tuning, and experimental validation of large antenna arrays.
</div>

Related developments in [iterative solvers and preconditioning](/projects/precond/) exploit similar subdomain and interface structures to improve convergence for large antenna systems. 

## Exploiting Repetitive Structures

(Semi-)Periodic electromagnetic structures contain substantial geometrical repetition, providing opportunities for computational reuse beyond conventional parallel domain decomposition. Instead of independently factorizing every repeated antenna subdomain, we construct reusable finite-element boundary representations through a **FETI-like compression procedure**.

Our [hierarchical FEM direct solver](/projects/direct_solver/) eliminates interior degrees of freedom and retains the electromagnetic response on subdomain boundaries. For identical or repeated array elements, the resulting local factorizations and boundary operators can be reused across multiple subdomains and excitations, substantially reducing the cost of large multi-element simulations.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid
            path="assets/img/projects/ap/ap_array_feti.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>

<div class="caption">
    Reusable subdomain factorizations and compressed boundary representations for repetitive antenna-array simulation, with comparison against measurement and conventional sparse direct solution.
</div>

More recently, the [direct DDM solver](/projects/direct_solver/) provides an alternative route by directly factorizing the global interface system.

## Efficient Open-Region Modeling

Antennas, FSSs, metasurfaces, and other radiating or scattering structures require accurate representation of the surrounding open domain. For finite-element models, the size and accuracy of this exterior region can have a substantial effect on the overall computational cost, particularly for electrically large or highly repetitive structures.

We integrate [higher-order absorbing boundary conditions](/projects/datai/) with the domain-decomposition framework to permit tightly bounded computational domains while maintaining accurate radiation characteristics over a wide range of incidence or scanning angles. Combined with reusable subdomain solution, this provides an efficient alternative to more computationally expensive integral-equation-based truncation for large electromagnetic structures.

<div class="row align-items-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid
            path="assets/img/projects/ap/ap_array_abc.png"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>

<div class="caption">
    Higher-order absorbing boundary treatment for tightly bounded simulation of a large antenna array, with radiation characteristics approaching integral-equation truncation at substantially reduced computational cost.
</div>

## Ongoing Research

Our current research extends these ideas toward **conformal and material-integrated antenna systems**. In planar repetitive arrays, identical subdomains provide a natural basis for reusing local matrices and factorizations. For curved and conformal arrays,
however, antenna elements may experience different orientations, geometrical mappings, and electromagnetic environments, making direct reuse considerably more challenging.

We are investigating how **hierarchical low-rank representations, reusable or parametrized subdomain operators, and effective material/interface models** can be combined within a common computational framework. The objective is to retain the computational advantages of repeated structures even when the individual subdomains are geometrically transformed or coupled to complex material environments.

Together with our work on [hierarchical direct solvers](/projects/direct_solver/) and [data-driven boundary and material operators](/projects/datai/), these developments target scalable full-wave simulation of large conformal arrays, engineered surfaces, and other complex antenna platforms.


<br>


## Selected Projects & Collaborations

- **Strange Beauty** project — Large-scale electromagnetic simulation for periodic electromagnetic structures — with *DSO National Laboratories, Singapore*

--

## Related Research

- [Domain Decomposition Methods](/projects/ddm/)
- [Iterative Solvers & Preconditioning](/projects/precond/)
- [Robust Direct Solvers](/projects/direct_solver/)
- [Scientific Data Learning](/projects/datai/)

--