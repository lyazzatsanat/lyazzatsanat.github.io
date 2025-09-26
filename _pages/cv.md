---
layout: single
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

{% assign cv_file = "/files/CV_Lyazzat_Sanat.pdf" %}

<p>
  You can view my CV below or 
  <a href="{{ cv_file | relative_url }}?v={{ site.time | date: '%s' }}" download>download it here</a>.
</p>

<iframe 
    src="{{ cv_file | relative_url }}?v={{ site.time | date: '%s' }}" 
    width="100%" 
    height="1000px" 
    style="border: 1px solid #ccc;">
  Your browser does not support PDFs. 
  <a href="{{ cv_file | relative_url }}?v={{ site.time | date: '%s' }}">Download the CV here</a>.
</iframe>
