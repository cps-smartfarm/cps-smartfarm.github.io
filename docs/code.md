---
layout: page
title: Code and Tutorials
subtitle: Sharing Farm Intelligence via Edge Computing
permalink: /code-and-tutorials/
image: /images/smart-ag.jpeg
---

<h3>A Real-time Gaming Framework for IoT and Smart Agriculture Teaching</h3>
<p>The Real-time Gaming Framework for IoT and Smart Agriculture is an educational project that introduces the concepts of IoT, sensor integration, MQTT protocol, and real-time data visualization through an interactive game. For source code, visit this <a href="https://github.com/Shakoor-Lab-Organization/learn_ioat" target="_blank">GitHub link</a>.</p>

<h2>Tutorials</h2>
<p>We have integrated tutorials to enhance understanding of remote sensing, GIS, and Machine Learning/Artificial Intelligence.</p>

<!-- Dynamically Fetch Tutorials Using GitHub API -->
<div id="tutorials-list"></div>

<script>
  // Fetching tutorials from the GitHub repository
  fetch('https://api.github.com/repos/missouriview/missouriview.github.io/contents/')
    .then(response => response.json())
    .then(data => {
      let tutorialsList = document.getElementById('tutorials-list');
      
      // Filtering out only the tutorials from the GitHub repository
      data.forEach(file => {
        if (file.name.endsWith('.html')) { // Assuming tutorials are HTML files
          let tutorialName = file.name.replace('.html', ''); // Remove file extension
          let tutorialUrl = file.html_url;

          // Create HTML to display each tutorial
          let listItem = document.createElement('div');
          listItem.innerHTML = `
            <h3>${tutorialName}</h3>
            <p>Learn more about ${tutorialName} here.</p>
            <a href="${tutorialUrl}" target="_blank">View Tutorial</a>
          `;
          tutorialsList.appendChild(listItem);
        }
      });
    })
    .catch(error => console.error('Error fetching tutorials:', error));
</script>
