---
layout: page
title: Image Registration
description: Digital Image Processing (ECE 278A) Course Project
img: /assets/projects/dip/airport_stitched.jpg
---

Implemented an algorithm to register images of a scene taken from different viewpoints and stitch them together to form a panorama. Used SIFT, RANSAC and Normalized DLT to solve this problem.


#### Input
---
<div class="img_row">
<img class="col one left" src="{{ site.baseurl }}/assets/projects/dip/airport_1.tif" alt="" title="drangon_without_PM"/>
<img class="col one right" src="{{ site.baseurl }}/assets/projects/dip/airport_2.tif" alt="" title="drangon_with_PM"/>
</div>
 
<div class="img">
<img class="col one left" src="{{ site.baseurl }}/assets/projects/dip/airport_3.tif" alt="" title="mirror_ball"/>
<img class="col one left" src="{{ site.baseurl }}/assets/projects/dip/airport_4.tif" alt="" title="importance_sampling"/>
<img class="col one left" src="{{ site.baseurl }}/assets/projects/dip/airport_5.tif" alt="" title="path_tracing"/>
</div>


### Output
---
<div class="img">
<img class="col three left" src="{{ site.baseurl }}/assets/projects/dip/airport_stitched.jpg" alt="" title="example image"/>
</div>
