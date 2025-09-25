---
layout: single
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

<p>
  You can view my CV below or 
  <a href="{{ '/files/CV_Lyazzat_Sanat.pdf' | relative_url }}" download>download it here</a>.
</p>

<!-- PDF viewer container -->
<div id="pdf-viewer" style="width: 100%; height: 90vh; border: 1px solid #ccc; overflow: auto;"></div>

<!-- PDF.js CSS & JS -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.9.179/pdf_viewer.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.9.179/pdf.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.9.179/pdf_viewer.min.js"></script>

<script>
  // URL of the PDF
  const url = "{{ '/files/CV_Lyazzat_Sanat.pdf' | relative_url }}";

  // PDF.js worker
  const pdfjsLib = window['pdfjs-dist/build/pdf'];
  pdfjsLib.GlobalWorkerOptions.workerSrc = 'https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.9.179/pdf.worker.min.js';

  const container = document.getElementById('pdf-viewer');

  // Load PDF
  pdfjsLib.getDocument(url).promise.then(pdf => {
    for (let i = 1; i <= pdf.numPages; i++) {
      pdf.getPage(i).then(page => {
        const scale = 1.2; // Adjust zoom
        const viewport = page.getViewport({ scale: scale });
        const canvas = document.createElement('canvas');
        canvas.style.display = 'block';
        canvas.style.margin = '10px auto';
        const context = canvas.getContext('2d');
        canvas.height = viewport.height;
        canvas.width = viewport.width;
        container.appendChild(canvas);
        page.render({ canvasContext: context, viewport: viewport });
      });
    }
  }).catch(error => {
    container.innerHTML = `<p>Failed to load PDF. <a href="${url}">Download CV here</a>.</p>`;
    console.error(error);
  });
</script>
