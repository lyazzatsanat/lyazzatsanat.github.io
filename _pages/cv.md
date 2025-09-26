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
{% assign cv_version = cv_file | file_modified: "%s" %}

<p>
  You can view my CV below or 
  <a href="{{ cv_file | relative_url }}?v={{ cv_version }}" download>download it here</a>.
</p>

<iframe 
    src="{{ cv_file | relative_url }}?v={{ cv_version }}" 
    width="100%" 
    height="1000px" 
    style="border: 1px solid #ccc;">
  Your browser does not support PDFs. 
  <a href="{{ cv_file | relative_url }}?v={{ cv_version }}">Download the CV here</a>.
</iframe>
