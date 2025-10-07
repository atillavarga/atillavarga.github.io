---
layout: page
title: "Copper Precursors for ALD"
description: "Development and characterization of novel copper precursors for ALD applications"
img: assets/img/bsc_thesis_cover.png
importance: 2
category: academic
published: true
thesis_pdf: Atilla_Varga_BSc_thesis.pdf
---

<div class="row">
  <div class="col-md-8">
    <h2>BSc Thesis: Copper Precursors for Atomic Layer Deposition</h2>

    <div class="card mb-4">
      <div class="card-body">
        <h5 class="card-title">Thesis Information</h5>
        <p class="card-text">
          <strong>Author:</strong> Atilla Varga<br>
          <strong>Institution:</strong> Carleton University<br>
          <strong>Supervisor:</strong> Dr. [Supervisor Name]<br>
          <strong>Date:</strong> [Thesis Completion Date]<br>
          <strong>Degree:</strong> Bachelor of Science in Chemistry
        </p>
      </div>
    </div>
  </div>

  <div class="col-md-4">
    <div class="text-center">
      {% if page.thesis_pdf %}
      <a href="{{ page.thesis_pdf | prepend: '/assets/pdf/' | relative_url }}" target="_blank" class="btn btn-primary btn-lg mb-3">
        <i class="fa-solid fa-file-pdf"></i> Download Full Thesis PDF
      </a>
      {% endif %}

      <div class="alert alert-info">
        <small><i class="fa-solid fa-info-circle"></i> Click to download and read the complete thesis</small>
      </div>
    </div>
  </div>
</div>

## Abstract

[Your thesis abstract here - this is a brief summary of your research, typically 200-300 words]

## Key Research Areas

### Introduction
[Brief introduction to your research topic and motivation]

### Materials and Methods
[Overview of materials used and experimental approaches]

### Results and Discussion
[Summary of key findings and their significance]

### Conclusion
[Main conclusions and future implications]

## Thesis Figures

<div class="row">
  <div class="col-md-6">
    {% include figure.html path="assets/img/thesis_figure1.png" title="Thesis Figure 1" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Figure 1: [Figure caption]</div>
  </div>
  <div class="col-md-6">
    {% include figure.html path="assets/img/thesis_figure2.png" title="Thesis Figure 2" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Figure 2: [Figure caption]</div>
  </div>
</div>


*This work was completed as part of the Bachelor of Science in Chemistry program at Carleton University.*
