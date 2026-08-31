---
layout: page
permalink: /people/
title: #people
description: #research group members
nav: true
nav_order: 5

_styles: >
    .people-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
        gap: 1.5rem;
        margin-top: 1rem;
        margin-bottom: 2rem;
    }

    .person-card {
        display: flex;
        align-items: flex-start;
        gap: 1rem;
    }

    .person-photo {
        width: 90px;
        height: 110px;
        object-fit: cover;
        border-radius: 4px;
        flex-shrink: 0;
    }

    .person-info {
        flex: 1;
    }

    .person-name {
        font-size: 1.05rem;
        font-weight: 600;
        margin-bottom: 0.15rem;
    }

    .person-role {
        font-size: 0.9rem;
        color: var(--global-theme-color);
        margin-bottom: 0.3rem;
    }

    .person-desc {
        font-size: 0.9rem;
        line-height: 1.45;
        color: var(--global-text-color-light);
    }
---

---

## Join the Group

> We are looking for motivated students interested in computational electromagnetics, scientific computing, and related areas.

> Prospective students with backgrounds in electrical engineering, applied mathematics, computational science, or related fields are welcome to contact me.

> Current opportunities may include:

- Ph.D. students
- Master students
- Undergraduate research students

> If you are interested, please send a brief introduction, CV, transcript, and a short description of your research interests by email.

---
<br><br>

## Research Group Members

<div class="people-grid">

  <div class="person-card">
    <img src="{{ '/assets/img/prof_pic.jpg' | relative_url }}" class="person-photo">
    <div class="person-info">
      <div class="person-name">Jiaqing Lu</div>
      <div class="person-role">Principal Investigator</div>
      <div class="person-desc">
        Computational electromagnetics, domain decomposition methods,
        fast solvers, and multiphysics modeling.
      </div>
    </div>
  </div>

</div>

<!-- ## Students -->

<div class="people-grid">

  <!-- Example student card -->
  <!--
  <div class="person-card">
    <img src="{{ '/assets/img/people/student-name.jpg' | relative_url }}" class="person-photo">
    <div class="person-info">
      <div class="person-name">
        <a href="/people/student-name/">Student Name</a>
      </div>
      <div class="person-role">Ph.D. Student</div>
      <div class="person-desc">
        Research interests: domain decomposition methods and fast solvers.
      </div>
    </div>
  </div>
  -->

</div>

<!-- ## Alumni -->

<div class="people-grid">

  <!-- Add former group members here in the future. -->

</div>