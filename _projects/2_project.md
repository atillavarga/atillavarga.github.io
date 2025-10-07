---
layout: page
title: "BSc Thesis: Copper Precursors for Atomic Layer Deposition"
description: "Development and characterization of novel copper precursors for ALD applications"
img: assets/img/thesis_cover.jpg
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

## Full Thesis Access

<div class="row mb-4">
  <div class="col-12">
    <div class="text-center mb-3">
      {% if page.thesis_pdf %}
      <a href="{{ page.thesis_pdf | prepend: '/assets/pdf/' | relative_url }}" target="_blank" class="btn btn-primary btn-lg me-2">
        <i class="fa-solid fa-file-pdf"></i> Download PDF
      </a>
      <button class="btn btn-outline-primary btn-lg" type="button" data-bs-toggle="collapse" data-bs-target="#pdfViewer" aria-expanded="false" aria-controls="pdfViewer">
        <i class="fa-solid fa-eye"></i> View Online
      </button>
      {% endif %}
    </div>

    <div class="collapse" id="pdfViewer">
      <div class="card">
        <div class="card-body p-0">
          <iframe src="{{ page.thesis_pdf | prepend: '/assets/pdf/' | relative_url }}" width="100%" height="600px" style="border: none;">
            <p>Your browser does not support iframes. <a href="{{ page.thesis_pdf | prepend: '/assets/pdf/' | relative_url }}">Click here to download the PDF</a></p>
          </iframe>
        </div>
      </div>
    </div>
  </div>
</div>

---

*This work was completed as part of the Bachelor of Science in Chemistry program at Carleton University.*


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}
```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
```
{% endraw %}
