---
layout: page
title: Software
description: software development, human-mahine interface 
img: assets/img/projects/project_software.png
importance: 10
category: application
research_id: hmi
permalink: /projects/hmi/
related_publications: false
---

Our computational methods have also been integrated into an in-house **finite-element and domain-decomposition electromagnetic simulation platform**. The software provides a unified environment for model configuration, domain-based meshing, numerical solution, and electromagnetic post-processing.

## Integrated Simulation Environment

The graphical interface organizes the complete simulation workflow, including material and excitation definitions, domain configuration, mesh generation, solver settings, and numerical simulation. Domain-based model organization allows individual regions to be configured and inspected independently while remaining part of the complete electromagnetic system.

<div class="row align-items-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid
            path="assets/img/projects/hmi/hmi_gui_main.jpg"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid
            path="assets/img/projects/hmi/hmi_gui_ddm_config.jpg"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>

<div class="caption">
    Integrated electromagnetic simulation environment and domain-based mesh configuration.
</div>


## Domain-Decomposition Modeling

Domain decomposition is directly incorporated into the modeling workflow. Interfaces between neighboring domains can be configured explicitly, while embedded domains allow localized structures to be introduced and modified independently within a larger computational model.

<div class="row align-items-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid
            path="assets/img/projects/hmi/hmi_gui_nonovlap_ddm.jpg"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid
            path="assets/img/projects/hmi/hmi_gui_embed_ddm.jpg"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>

<div class="caption">
    Configuration of domain interfaces for nonconformal and embedded domain decomposition modeling.
</div>


## Simulation & Post-Processing

The simulation environment connects numerical solution with electromagnetic post-processing, including multiport S-parameters, field distributions, and radiation characteristics. Results from different excitations and frequencies can be inspected within the same workflow.

<div class="row align-items-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid
            path="assets/img/projects/hmi/hmi_gui_param_post.jpg"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.liquid
            path="assets/img/projects/hmi/hmi_gui_field_visual.jpg"
            class="img-fluid rounded z-depth-0"
            zoomable=true
        %}
    </div>
</div>

<div class="caption">
    Electromagnetic post-processing for multiport responses, field distributions, and radiation characteristics.
</div>
