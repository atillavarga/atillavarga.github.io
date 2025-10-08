---
layout: page
title: "Infiltration of 3D Printed Polymers"
description: "Enhancing 3D Printed Substrates Using Atomic Layer Deposition"
img: assets/img/msc_cover_image.png
importance: 3
category: academic
published: true
thesis_pdf: Atilla_Varga_MSc_thesis.pdf
---

<div class="row">
  <div class="col-md-8">
    <div class="card mb-4">
      <div class="card-body">
        <h5 class="card-title">Thesis Information</h5>
        <p class="card-text">
          <strong>Author:</strong> Atilla Varga<br>
          <strong>Institution:</strong> Carleton University<br>
          <strong>Supervisor:</strong> Prof. Sean Barry<br>
          <strong>Date:</strong> July 2022<br>
          <strong>Degree:</strong> Master of Science in Chemistry
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
    </div>
  </div>
</div>

## Abstract

My masters thesis focused on the integration of 3D printing and Atomic Layer Deposition (ALD) to create advanced 3D printed architectures. `ALD` was used in combination with common and inexpensive polymer materials post model creation (using 3D printing) to create nanoscale hybrid materials. 3D printed Acrylonitrile Butadiene Styrene (ABS) and Polyvinyl Alcohol (PVA) polymer structures were coated and infiltrated with alumina (Al2O3) using the trimethylaluminum(III) (TMA) and water ALD process. Coating 3D printed structures resulted in a protective overcoating resisting plasma, and solvent exposure; Infiltration resulted in enhanced thermal characteristics.

<br>

## Modified Material Example

Below is a video of two `benchy` structures which were printed in ABS; an untreated one (left), and one coated in Alumina using a `TMA` and water ALD process (right).
Both structures were placed on a stage in a desiccator with ~20 mL of acetone at the bottom. Time is in Hours:Minutes.

<div class="row">
  <div class="col-md-6">
    {% include figure.html path="assets/img/masters_figure1.png" title="Master's Thesis Figure 1" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Figure 1: [Figure caption]</div>
  </div>

<br>

*This work was completed as part of the Masters of Science in Chemistry program at Carleton University.*





