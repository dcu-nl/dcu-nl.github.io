---
permalink: /publications/
title: "Publications"
last_modified_at: 2026-03-17
---

{% bibliography %}

<script>
// Make DOI URLs clickable in the bibliography
document.addEventListener('DOMContentLoaded', function() {
  // Find all text nodes in the bibliography and look for DOI URLs
  const walker = document.createTreeWalker(
    document.body,
    NodeFilter.SHOW_TEXT,
    null,
    false
  );

  const nodesToReplace = [];
  let node;
  while (node = walker.nextNode()) {
    if (node.textContent.match(/https?:\/\/doi\.org\/[^\s<>,)]+/)) {
      nodesToReplace.push(node);
    }
  }

  // Replace DOI text with clickable links
  nodesToReplace.forEach(textNode => {
    const span = document.createElement('span');
    span.innerHTML = textNode.textContent.replace(
      /(https?:\/\/doi\.org\/[^\s<>,)]+)/g,
      '<a href="$1" target="_blank" rel="noopener noreferrer">$1</a>'
    );
    textNode.parentNode.replaceChild(span, textNode);
  });
});
</script>

