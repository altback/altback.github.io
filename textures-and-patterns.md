---
layout: normal
title: Textures and Patterns
---
 <div class="jumbotron jumbotron-fluid">
  <div class="container">
    <h1 class="text-center text-banner font-weight-bold text-title">Textures and Patterns</h1><!-- Card padding is custom css added to have a proper space between h1 and cards -->
    {% assign no_of_videos = site.data.textures-and-patterns | size %}
    {% assign count = 0 %}
    {% assign half = no_of_videos | divided_by: 2 %}
    {% for item in (1..half) %}
      {% if site.data.textures-and-patterns.first %}
         <div class="card-deck mb-3 text-center card-padding">
           {% for j in (1..2) %}
            <div class="card mb-4 box-shadow">
              <div class="card-header">
                <h4 class="my-0 font-weight-normal text-title"><strong>{{ site.data.textures-and-patterns[count].texture_title }}</strong></h4>
              </div>
              <div class="card-body">
                <div>
                  <a href="{{ site.data.textures-and-patterns[count].texture_link }}"><img src="{{ site.data.textures-and-patterns[count].texture_image }}" class="img-fluid" alt="{{ site.data.textures-and-patterns[count].texture_image_alttext }}"></a>
                </div>
                <h5><br>{{site.data.textures-and-patterns[count].texture_description }}</h5><br>
                <p><span class="font-weight-bold">Resource type:</span> {{ site.data.textures-and-patterns[count].resource-type }}</p>
                <ul class="list-unstyled mt-3 mb-4">
                  <li class="font-weight-bold">download-links:</li>
                  {% for entry in site.data.textures-and-patterns[count].download-links %}
                   <li class="download-links">{{ entry.link }}
                   </li><br>
                  {% endfor %}
                </ul>
              </div>
            </div>
            {% assign count = count | plus:1 %}
           {% endfor %}
         </div>

      {% endif %}
    {% endfor %}
    {% assign odd_videos = no_of_videos | modulo: 2 %}
    {% if odd_videos != 0 %}
      <div class="card-deck mb-3 text-center">
        <div class="card mb-4 box-shadow">
          <div class="card-header">
            <h4 class="my-0 font-weight-normal text-title"><strong>{{ site.data.textures-and-patterns[count].texture_title }}</strong></h4>
          </div>
          <div class="card-body">
          <div>
            <a href="{{ site.data.textures-and-patterns[count].texture_link }}"><img src="{{ site.data.textures-and-patterns[count].texture_image }}" class="img-fluid" alt="{{ site.data.textures-and-patterns[count].texture_image_alttext }}"></a>
          </div>
            <h5><br>{{site.data.textures-and-patterns[count].texture_description }}</h5><br>
            <p><span class="font-weight-bold">Resource type:</span> {{ site.data.textures-and-patterns[count].resource-type }}</p>
            <p><span class="font-weight-bold">Application tested with:</span> {{ site.data.textures-and-patterns[count].app-tested }}</p>
            <ul class="list-unstyled mt-3 mb-4">
              <li class="font-weight-bold">download-links:</li>
              {% for entry in site.data.textures-and-patterns[count].download-links %}
               <li class="download-links">{{ entry.link }}
               </li><br>
              {% endfor %}
            </ul>
          </div>
        </div>
      </div>
    {% endif %}
  </div>
</div>
