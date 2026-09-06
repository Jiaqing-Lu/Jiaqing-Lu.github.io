---
layout: page
title: Scientific Data Learning
description: data-driven methods for scientific computing
img: assets/img/6.jpg
importance: 9
category: algorithm
research_id: learndata
permalink: /projects/learndata/
related_publications: true
---

Scientific computing increasingly involves information that is not most naturally represented by explicit analytical models. Our research explores **data-driven and randomized numerical methods** for CEM, with an emphasis on incorporating physical structure into the learning and approximation process.

Rather than replacing physics-based simulation, these methods are used to **construct numerical models from EM response data, identify low-dimensional structures in large systems, and accelerate conventional full-wave computation**.


## Higher-Order Absorbing Boundary Conditions

Absorbing boundary conditions (ABCs) provide compact approximations of EM radiation into an unbounded exterior domain. 
The conventional first-order ABC primarily absorbs the waves normal to boundary yet struggling with oblique incident angles. 
Existing second-order ABCs, PMLs, and IE truncations also come with their own complexities and limitations.

We developed an improved **higher-order ABC** in which the boundary operator is constructed from the desired reflection responses of incident EM waves.
By selecting representative TE and TM plane-wave conditions, the coefficients of the boundary operator can be determined directly from their EM responses. The resulting formulation introduces additional angular information beyond the conventional first-order ABC, while auxiliary surface variables allow its implementation without requiring smooth truncation boundaries.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/learndata/learndata_abc.png"
            class="img-fluid rounded z-depth-0" 
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    The formulation and application of data-driven ABC.
</div>

This perspective provides a route toward constructing **problem-adapted boundary operators from sampled EM responses**, rather than restricting their forms entirely through analytical derivation.


## Higher-Order Impedance & Transition Conditions

The same idea can be extended from ABC to **higher-order impedance boundary conditions (IBCs) or more general transition conditions (GTCs)**. In the ABC formulation, the boundary operator is determined from prescribed reflection behavior of incident waves. For a penetrable or metasurface-type structure, this idea is naturally generalized by considering both reflection and transmission responses.

For geometrically complex structures such as frequency-selective surfaces or metamaterial layers, representative TE and TM scattering data are first obtained over different incidence conditions. Effective IBCs or GTCs can then be constructed to replace the original fine-scale structures in CEM simulations, substantially reducing geometrical and computational complexity.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/learndata/learndata_gtc.png"
            class="img-fluid rounded z-depth-0" 
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    The formulation and application of data-driven IBC/GTC.
</div>

This work forms part of our broader interest in learning compact physical operators from electromagnetic response data.


## Randomized PCA & Matrix Learning

Large electromagnetic systems frequently contain **hidden low-dimensional structures** even when their original matrix representations are extremely large. We employ randomized sampling and principal component analysis (PCA) to identify these structures without explicitly constructing or decomposing the complete dense operators.

For domain decomposition systems, randomized excitations are applied to sample the system response, while an adaptive PCA procedure extracts a reduced basis for constructing efficient preconditioners. Related randomized low-rank techniques are also incorporated into hierarchical direct solvers, where sampled matrix interactions are compressed during recursive skeletonization and factorization.

These approaches combine **randomized numerical linear algebra with the physical and geometrical structures of CEM systems**, providing reduced representations directly within conventional electromagnetic solvers.

<div class="row align-items-center justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid 
            path="assets/img/projects/learndata/learndata_pca.png"
            class="img-fluid rounded z-depth-0" 
            zoomable=true
        %}
    </div>
</div>
<div class="caption">
    Representative application of randomized matrix techniques.
</div>

## Ongoing Research

Our ongoing research explores the integration of **machine learning with physics-based CEM algorithms**, with the objective of assisting rather than replacing established numerical solvers, such as combining learned models with FEM, domain decomposition, and reduced-order computation.
Another direction investigates **data learning for IC and PCB analysis**, where large collections of geometrical, material, circuit, and electromagnetic data
can be used to identify correlations between physical design parameters and system-level electromagnetic behavior.


<br>

## Selected Projects & Collaborations

-  Higher-Order Absorbing Boundary Conditions & Incorporate Generalized Impedance Boundary Condition into FEM formulation -- collaborative research with *Ansys, Inc.* 

- Earlier ABC & IBC research was conducted in collaboration with Dr. Jingyue Zhang and Prof. Jin-Fa Lee at The Ohio State University.

--

## Related Research

- [Iterative Solvers & Preconditioning](/projects/precond/)
- [Robust Direct Solvers](/projects/direct_solver/)
- [Multiscale Electronics Modeling](/projects/ic/)
- [Antenna & Material Modeling](/projects/ap/)
