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
    <div class="card mb-4">
      <div class="card-body">
        <h5 class="card-title">Thesis Information</h5>
        <p class="card-text">
          <strong>Author:</strong> Atilla Varga<br>
          <strong>Institution:</strong> Carleton University<br>
          <strong>Supervisor:</strong> Prof. Sean Barry<br>
          <strong>Date:</strong> April 2020<br>
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

Copper metal thin films continue to be used as an interconnect material for silicon integrated circuits. Copper reduces propagation delays, power consumption, and size of the interconnects in the circuits, which makes it a highly sought-after metal in the field of nanotechnology. Atomic layer deposition (ALD) is a layer by layer, self-limiting, thin film deposition technique excels at depositing nanoscale films. However, the thickness of the copper film needs to be reduced to <2 nm to keep up with the ever-decreasing size. This implies that the ligand attached to the copper precursor needs to promote a self-limiting behaviour of the compound for better conformality and perform better than the currently available precursors. We can use N-heterocyclic carbenes (NHCs) as the self-limiting behaviour promoting ligand in ALD to increase the conformality of the film. Such a concept hasn’t been described before in the field, although NHC’s are known to bind strongly to metallic surfaces as a self-assembled monolayer. Our group has developed a general framework for coinage metal precursors where one ligand is the intended self-limiting ligand (NHC) and the other ligand leaves the surface upon chemisorption. The above framework seems to work; however, the precursor is not thermodynamically stable enough to survive the delivery temperature. Therefore, different leaving ligands (CF3 and methyl(trimethylsilyl)) and a different NHC (isopropyl side groups) were synthesized and tested. The best leaving ligand was determined to be methyl(trimethylsilyl), which when paired with the isopropyl NHC sufficiently increased the thermal stability and volatility of the resulting precursor. The onset of thermal decomposition and 1 Torr temperature was 188 °C and 143 °C respectively, giving a thermal range of 45 °C.

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
