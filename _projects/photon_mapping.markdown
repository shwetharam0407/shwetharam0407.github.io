---
layout: page
title: Photon Mapping
description: Advanced Image Synthesis (ECE 594Q) Course Project
img: /assets/projects/photon_mapping/Dragon/dragonwithPM.bmp
---

Photon Mapping is a two-pass rendering algorithm that approximately solves the rendering equation by tracing light rays from the light source and the camera. I implemented this algorithm for my final course project and demonstrated that PM can handle caustics and diffuse inter-reflections well. Here is a sample render.

<div class="img_row">
<img class="col one left" src="{{ site.baseurl }}/assets/projects/photon_mapping/Dragon/dragonwithoutPM.bmp" alt="" title="drangon_without_PM"/>
    <img class="col one right" src="{{ site.baseurl }}/assets/projects/photon_mapping/Dragon/dragonwithPM.bmp" alt="" title="drangon_with_PM"/>
</div>
<div class="col three caption">
    Dragon without (left) and with (right) Photon Mapping
</div>


Advanced Image Synthesis course involved a series of projects through which I learnt about physically-based rendering. I built a raytracer from scratch and implemented importance sampling, image-based lighting and path tracing. Here's a showcase of some of the images synthesized by the renderer I built for this course.

<div class="img">
<img class="col one left" src="{{ site.baseurl }}/assets/projects/photon_mapping/mirror_ball.bmp" alt="" title="mirror_ball"/>
<img class="col one left" src="{{ site.baseurl }}/assets/projects/photon_mapping/withimportancesampling.bmp" alt="" title="importance_sampling"/>
<img class="col one left" src="{{ site.baseurl }}/assets/projects/photon_mapping/ColorBleeding-diffuse-diffuse.bmp" alt="" title="path_tracing"/>
</div>
<div class="col three caption">
Left: Image-based Lightning. MIddle: Importance Sampling. Right: Path Tracing.
</div>
