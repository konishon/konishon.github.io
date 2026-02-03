---
layout: page
title: Projects
permalink: /projects/
---

<section class="projects-section">
  <div class="section-header">
    <h2>Technical Projects</h2>
    <p>A showcase of my development work and open-source contributions</p>
  </div>

  <div class="projects-grid">
    {% for repo in site.github.public_repositories %}
      {% if repo.fork == false and repo.topics.size > 0 %}
        <div class="project-card">
          <h3><a href="{{ repo.html_url }}" target="_blank" rel="noopener">{{ repo.name }}</a></h3>
          <p class="project-description">{{ repo.description }}</p>
          
          {% if repo.topics.size > 0 %}
            <div class="tech-stack">
              {% for topic in repo.topics %}
                <span class="tech-tag">{{ topic }}</span>
              {% endfor %}
            </div>
          {% endif %}
          
          <div class="project-meta">
            Last updated: {{ repo.updated_at | date: "%B %-d, %Y" }}
          </div>
        </div>
      {% endif %}
    {% endfor %}
  </div>
</section>
