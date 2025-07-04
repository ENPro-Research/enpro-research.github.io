---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
lang: de
permalink: /
title: ENPro-Research
description: Website des Forschungsprojekts ENPro
---

<section class="background-light pad" id="info">
    <div class="container text-justify">
        <h1>Projektinformationen</h1>
        <div class="row">
            <div class="col-lg-12 col-md-12">
                <p class="text-justify">
                Das Projekt Energy Neutral Production wird durch das Land Oberösterreich finanziert als Teil des Programms #upperVISION2030. Nähere Informationen dazu unter www.uppervision.at.
                </p>
                <p class="text-justify">
                Mit dem vom Land OÖ geförderten Projekt ENPro (Energy Neutral Production) verfolgt die FH OÖ das Ziel, durch Modellierung, Simulation und Optimierung neue Wege zur energieeffizienten und perspektivisch energieneutralen Produktion aufzuzeigen. Der Projektstart erfolgte im Frühjahr 2025. Federführend ist das Center of Excellence for Smart Production, beteiligt sind Standorte aus Hagenberg, Steyr und Wels. Im Mittelpunkt des Projekts steht die Frage, wie produzierende Unternehmen auf Basis bestehender Energieerzeugungs- und Speichertechnologien ihre Produktionsprozesse so gestalten können, dass Energieverbrauch, CO2-Ausstoß und Netzbelastung deutlich reduziert werden. 
                </p>
            </div>
        </div>
    </div>
</section>

<!-- Info Section -->
<section class="page-section" id="info">
    <div class="container">
        <div class="text-center">
            <h2 class="section-heading text-uppercase">{{ site.data.i18n.t.sections.info.title[site.active_lang] }}</h2>
            <h3 class="section-subheading text-muted">{{ site.data.i18n.t.sections.info.subtitle[site.active_lang] }}</h3>
        </div>
        <div class="row text-center">
            {% for technique in site.data.i18n.t.sections.info.techniques %}
            <div class="col-md-4">
                <span class="fa-stack fa-4x">
                    <i class="fas fa-circle fa-stack-2x feature-badge"></i>
                    <i class="fas fa-{{ technique.icon }} fa-stack-1x fa-inverse"></i>
                </span>
                <h4 class="my-3">{{ technique.title[site.active_lang] }}</h4>
                <p class="text-muted">{{ technique.text[site.active_lang] }}</p>
            </div>
            {% endfor %}
        </div>
    </div>
</section>

<section class="background-dark pad" id="blog">
    <div class="container">
        <h1>Von unserem Blog...</h1>
        {% if site.posts.size > 0 %}
        <div class="row">
            <div class="col-lg-12 col-md-12">
                {% for post in site.posts limit:1 %}
                    {% include post_preview.html preview_size_small=true %}
                {% endfor %}
            </div>
        </div>
        <div class="row">
            <div class="col-lg-12 text-right">
                <a href="/blog" id="btn-blog" class="btn btn-xl btn-slim-primary blog-button">Mehr Posts</a>
            </div>
        </div>
        {% else %}
        <div class="row"><div class="col-lg-12"><h4>Sorry, there are currently no posts available.</h4></div></div>
        {% endif %}
    </div>
</section>

<!-- Team Section -->
<section class="page-section bg-light" id="team">
    <div class="container">
        <div class="text-center">
            <h2 class="section-heading text-uppercase">{{ site.data.i18n.t.team.title[site.active_lang] }}</h2>
            <h3 class="section-subheading text-muted">{{ site.data.i18n.t.team.subtitle[site.active_lang] }}</h3>
        </div>
        <div class="row">
            {% for member in site.data.i18n.t.team.members %}
            <div class="col-lg-4">
                <div class="team-member">
                    <img class="mx-auto" src="{{ 'assets/img/team/' | append: member.img | relative_url }}" alt="{{ member.name }}" />
                    <h4>{{ member.name }}</h4>
                    <p class="text-muted">{{ member.position }}</p>
                </div>
            </div>
            {% endfor %}
        </div>    
    </div>
</section>
<section class="page-section background-dark pad" id="contact">
    <div class="container text-justify">
        <h2 class="section-heading">Kontakt</h2>
        <div class="row contact-info">
            <div class="col-lg-6 col-md-12">
                <h4>Manuel Brunner</h4>
                <table class="info-table">
                    <tr><td>Rolle:</td><td>Administrativer Projektleiter</td></tr>
                    <tr><td>Tel:</td><td>+43 5 0804 33293</td></tr>                  
                    <tr><td>Mail:</td><td><a href="mailto:Manuel.Brunner@fh-steyr.at">Manuel.Brunner@fh-steyr.at</a></td></tr>
                </table>
            </div>
        </div>
    </div>
</section>
<section>
  <script>
    const map = L.map('map').setView([48.2, 14.2], 10);

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; OpenStreetMap contributors'
    }).addTo(map);
    
    const locations = [
      { lat: 48.368369, lng: 14.514283, name: "FH OÖ Campus Hagenberg" },
      { lat: 48.043031, lng: 14.418338, name: "FH OÖ Campus Steyr" },
      { lat: 48.161402, lng: 14.027811, name: "FH OÖ Campus Wels" }
    ];

    locations.forEach(loc => {
      L.marker([loc.lat, loc.lng]).addTo(map).bindPopup(loc.name);
    });
  </script>
</section>

[ffg]: https://www.ffg.at/AI-Region-UpperAustria
[uv]: https://www.uppervision.at/
