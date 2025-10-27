---
layout: page
title: "Gold Digestion"
description: "Dissolving gold for synthesis of gold precursors"
img: assets/img/gold_digestion.png
importance: 3
category: Academic
published: true
---

## The Project

In university, we needed to make gold precursors for atomic layer deposition, but buying gold chloride was really expensive. Instead of spending a fortune on commercial chemicals, we came up with a cheaper way - we bought pure gold from the Royal Mint and dissolved it ourselves using chlorine gas.

## Why This Matters

Gold chloride from chemical suppliers costs a lot because it's a specialty chemical. But gold bullion from the Royal Mint is much cheaper per gram of gold. By digesting the gold ourselves, we cut the costs by about 70%. This made our research more affordable and showed how to be resourceful in the lab.

## How We Did It

We started with high-purity gold (99.99%) from the Royal Mint. The gold came as small pieces that we could handle easily. We built a reaction setup where we could heat the gold and pass chlorine gas over it.

<div class="row justify-content-center">
    <div class="col-md-8">
        {% include figure.html path="assets/img/gold_digestion.png" title="Gold digestion setup" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Our custom setup for dissolving gold with chlorine gas.
</div>

The reaction took place at around 300-350°C with a steady flow of chlorine gas. It took a few hours, but we ended up with gold chloride that we could use just like the expensive commercial stuff.

## Making the Precursor

Once we had the gold chloride, we reacted it with other chemicals to make a gold precursor suitable for ALD. We used ligands that would make the compound volatile enough to evaporate in the deposition chamber.

The final product was tested to make sure it had the right properties - it needed to be stable, volatile, and leave behind pure gold films when heated.

## Safety First

Working with chlorine gas requires careful safety measures. We did all the reactions in a fume hood with proper ventilation and gas monitoring. Everyone wore protective equipment and we had emergency procedures in place. Gold compounds can also be hazardous, so we handled them with care and disposed of waste properly.

## What We Learned

This project taught us that sometimes the most expensive chemicals aren't necessary if you can make them yourself. It also showed how to work safely with corrosive gases and precious metals. The method we developed could be useful for other researchers who need gold compounds but want to keep costs down.

---

*This was part of my undergraduate research in chemistry, where we learned to be creative with lab resources.*


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
