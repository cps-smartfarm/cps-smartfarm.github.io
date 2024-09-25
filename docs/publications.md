---
layout: page
title: Publications
subtitle: Papers published from our research activities
permalink: /publications/
image: /images/smart-ag.jpeg
---
{% assign publications_by_year = site.data.publications | group_by: 'year' %}
<style>
    /* Basic lightbox styling */
    .lightbox-overlay {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.8);
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }

    .lightbox-content {
      background: white;
      padding: 20px;
      border-radius: 8px;
      max-width: 90%;
      max-height: 90%;
      overflow-y: auto;
    }

    .lightbox-close {
      position: absolute;
      top: 20px;
      right: 20px;
      color: white;
      font-size: 24px;
      cursor: pointer;
    }
</style>

<!-- Lightbox Structure -->
<div id="lightbox" class="lightbox-overlay">
  <div class="lightbox-content" id="lightbox-content">
    <!-- Dynamic content will be loaded here -->
  </div>
  <span class="lightbox-close" id="lightbox-close">&times;</span>
</div>
<ul>
{% for year_group in publications_by_year %}
  <li>{{ year_group.name }}</li>
  <ul>
    {% for publication in year_group.items %}
      <li class="publication">{{ publication.citation }}</li>
    {% endfor %}
  </ul>
{% endfor %}
</ul>
<script>
  // Function to fetch and display BibTeX content
  function fetchBibTeXContent(url) {
    fetch(url)
      .then(response => {
        if (!response.ok) {
          throw new Error('Network response was not ok');
        }
        return response.text();
      })
      .then(data => {
        // Display the BibTeX content in the lightbox
        document.getElementById('lightbox-content').textContent = data;
        document.getElementById('lightbox').style.display = 'flex';
      })
      .catch(error => {
        document.getElementById('lightbox-content').textContent = 'Error loading content: ' + error.message;
        document.getElementById('lightbox').style.display = 'flex';
      });
  }

  // Add event listeners to links with class 'bibtex'
  document.querySelectorAll('.bibtex').forEach(function(link) {
    link.addEventListener('click', function(event) {
      event.preventDefault(); // Prevent default link behavior

      // Fetch the BibTeX content from the external URL
      const bibtexUrl = this.getAttribute('href');
      fetchBibTeXContent(bibtexUrl);
    });
  });

  // Close the lightbox when the close button is clicked
  document.getElementById('lightbox-close').addEventListener('click', function() {
    document.getElementById('lightbox').style.display = 'none';
  });

  // Close the lightbox if user clicks outside the content
  document.getElementById('lightbox').addEventListener('click', function(event) {
    if (event.target === this) {
      this.style.display = 'none';
    }
  });
</script>

