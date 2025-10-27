---
layout: page
title: "Copper Precursors for ALD"
description: "Development and characterization of novel copper precursors for ALD applications"
img: assets/img/bsc_thesis_cover.png
importance: 2
category: Projects
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
    </div>
  </div>
</div>

## Abstract

Copper metal thin films continue to be used as an interconnect material for silicon integrated circuits. Copper reduces propagation delays, power consumption, and size of the interconnects in the circuits, which makes it a highly sought-after metal in the field of nanotechnology. Atomic layer deposition (ALD) is a layer by layer, self-limiting, thin film deposition technique that excels at depositing nanoscale films. However, the thickness of the copper film needs to be reduced to <2 nm to keep up with the ever-decreasing size. This implies that the ligand attached to the copper precursor needs to promote a self-limiting behaviour of the compound for better conformality and perform better than the currently available precursors. We can use N-heterocyclic carbenes (NHCs) as the self-limiting behaviour promoting ligand in ALD to increase the conformality of the film. Such a concept hasn’t been described before in the field, although NHC’s are known to bind strongly to metallic surfaces as a self-assembled monolayer. Our group has developed a general framework for coinage metal precursors where one ligand is the intended self-limiting ligand (NHC) and the other ligand leaves the surface upon chemisorption. The above framework seems to work; however, the precursor is not thermodynamically stable enough to survive the delivery temperature. Therefore, different leaving ligands (CF3 and methyl(trimethylsilyl)) and a different NHC (isopropyl side groups) were synthesized and tested. The best leaving ligand was determined to be methyl(trimethylsilyl), which when paired with the isopropyl NHC sufficiently increased the thermal stability and volatility of the resulting precursor. The onset of thermal decomposition and 1 Torr temperature was 188 °C and 143 °C respectively, giving a thermal range of 45 °C.

<br>

### Synthesis Route
Overview of the synthesis steps, beginning with the common starting material.
{% include figure.html path="assets/img/starting_salt.png" title="starting material" class="img-fluid rounded z-depth-1" %}

Further synthesis of Copper NHC precursors.
{% include figure.html path="assets/img/precursors_synthesis.png" title="copper precursors" class="img-fluid rounded z-depth-1" %}

<br>

### Results
The best ALD precursor candidate was the NHC-Cu-NeoSi precursor with the following volatility and thermal stability characteristics.

NHC-Cu_NeoSi <span data-bs-toggle="tooltip" data-bs-placement="top" title="Thermogravimetric Analysis - a measurement of a material's mass change as a function of temperature">`TGA`</span> with an onset of vaporization at 100 °C and 1 Torr temperature at 143 °C.
{% include figure.html path="assets/img/neosi_cu_tga.png" title="neosi tga" class="img-fluid rounded z-depth-1" %}

NHC-Cu_NeoSi <span data-bs-toggle="tooltip" data-bs-placement="top" title="Differential Scanning Calorimetry - a measurement of heat flow between a sample and a reference. Downward peaks represent endothermic events (heat absorption) and upward peaks show exothermic events (heat release).">`DSC`</span> with a decomposition point at 200 °C.
{% include figure.html path="assets/img/neosi_cu_dsc.png" title="neosi dsc" class="img-fluid rounded z-depth-1" %}

NHC-Cu_NeoSi <span data-bs-toggle="tooltip" data-bs-placement="top" title="A QCM (Quartz Crystal Microbalance) mass gain experiment showing mass gain with increasing precursor dosage (pulse length).">`saturation curve`</span> curve showing self-limiting growth behaviour. 
{% include figure.html path="assets/img/neosi_cu_saturation.png" title="neosi saturation curve" class="img-fluid rounded z-depth-1" %}

<br>
### Homemade ALD Tool
The saturation curve and ALD experiments were performed on a home-built ALD tool.
{% include figure.html path="assets/img/homemade_ald_tool.png" title="homemade ald tool model" class="img-fluid rounded z-depth-1" %}
{% include figure.html path="assets/img/homemade_ald_actual.png" title="homemade ald tool" class="img-fluid rounded z-depth-1" %}

<br>

*This work was completed as part of the Bachelor of Science in Chemistry program at Carleton University.*
