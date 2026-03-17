---
permalink: /publications/
title: "Publications"
last_modified_at: 2026-03-17
---

{% bibliography %}

<script>
// Convert DOI URLs to clickable links
document.addEventListener('DOMContentLoaded', function() {
  const doiRegex = /https:\/\/doi\.org\/([^\s<>,)]+)/g;
  
  function processNode(node) {
    if (node.nodeType === Node.TEXT_NODE) {
      const text = node.textContent;
      if (doiRegex.test(text)) {
        const span = document.createElement('span');
        span.innerHTML = text.replace(doiRegex, '<a href="https://doi.org/$1" target="_blank" rel="noopener noreferrer">https://doi.org/$1</a>');
        node.parentNode.replaceChild(span, node);
      }
    } else if (node.nodeType === Node.ELEMENT_NODE && node.nodeName !== 'A' && node.nodeName !== 'SCRIPT' && node.nodeName !== 'STYLE') {
      const children = Array.from(node.childNodes);
      children.forEach(processNode);
    }
  }
  
  const bibDiv = document.querySelector('.js-results-container') || document.querySelector('[role="main"]') || document.body;
  processNode(bibDiv);
});
</script>

