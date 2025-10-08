---
layout: page
title: "ALD Infiltration of 3D Printed Polymers"
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

      <div class="alert alert-info">
        <small><i class="fa-solid fa-info-circle"></i> Click to download and read the complete thesis</small>
      </div>
    </div>
  </div>
</div>

## Abstract

[Your master's thesis abstract here - this should summarize your research, methodology, key findings, and significance]

## Introduction

[Introduction content - background, research objectives, and significance of your work]

## Materials and Methods

[Description of materials used and experimental methodologies]

## Results and Discussion

[Presentation and analysis of your research findings]

## Conclusion

[Summary of key findings, implications, and future work]

## Key Figures

<div class="row">
  <div class="col-md-6">
    {% include figure.html path="assets/img/masters_figure1.png" title="Master's Thesis Figure 1" class="img-fluid rounded z-depth-1" %}
    <div class="caption">Figure 1: [Figure caption]</div>
  </div>
  <div class="col-md-6">
    {% include figure.html path="assets/img/masters_figure2.png" title="Master's Thesis Figure 2" class="img-fluid rounded z-depth-1" %}
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
      <button class="btn btn-outline-primary btn-lg" type="button" data-bs-toggle="collapse" data-bs-target="#mastersPdfViewer" aria-expanded="false" aria-controls="mastersPdfViewer">
        <i class="fa-solid fa-eye"></i> View Online
      </button>
      {% endif %}
    </div>

    <div class="collapse" id="mastersPdfViewer">
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

*This work was completed as part of the Master of Science in Chemistry program at Carleton University.*


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
