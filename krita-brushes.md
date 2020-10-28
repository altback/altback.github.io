---
layout: normal
title: Brushes for Krita
---
 <div class="jumbotron jumbotron-fluid">
  <div class="container">
    <h1 class="text-center text-banner font-weight-bold text-title">Brushes for Krita</h1><!-- Card padding is custom css added to have a proper space between h1 and cards -->
    {% assign no_of_videos = site.data.krita-brushes | size %}
    {% assign count = 0 %}
    {% assign half = no_of_videos | divided_by: 2 %}
    {% for item in (1..half) %}
      {% if site.data.krita-brushes.first %}
         <div class="card-deck mb-3 text-center card-padding">
           {% for j in (1..2) %}
            <div class="card mb-4 box-shadow">
              <div class="card-header">
                <h4 class="my-0 font-weight-normal text-title"><strong>{{ site.data.krita-brushes[count].videotitle }}</strong></h4>
              </div>
              <div class="card-body">
                 {% if site.data.krita-brushes[count].videotype == 'youtube' %}
                 <div class="embed-responsive embed-responsive-16by9">
                   <iframe src="https://www.youtube.com/embed/{{ site.data.krita-brushes[count].videoID }}" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                  </div>
                   {% elsif site.data.krita-brushes[count].videotype == 'vimeo' %}
                  <div class="embed-responsive embed-responsive-16by9">
                   <iframe src="https://player.vimeo.com/video/{{ site.data.krita-brushes[count].videoID }}" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                  </div>
                 {% endif %}
                
                {% if site.data.krita-brushes[count].videotype == 'image' %}
                   <a href="{{ site.data.krita-brushes[count].image-link }}"><img src="{{ site.data.krita-brushes[count].image-path }}" class="img-fluid" alt="{{ site.data.krita-brushes[count].image-alttext }}"></a>
                {% endif %}
                <h5><br>{{site.data.krita-brushes[count].videodescription }}</h5><br>
                <p><span class="font-weight-bold">Resource type:</span> {{ site.data.krita-brushes[count].resource-type }}</p>
                <p><span class="font-weight-bold">Application tested with:</span> {{ site.data.krita-brushes[count].app-tested }}</p>
                <ul class="list-unstyled mt-3 mb-4">
                  <li class="font-weight-bold">download-links:</li>
                  {% for entry in site.data.krita-brushes[count].download-links %}
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
            <h4 class="my-0 font-weight-normal text-title"><strong>{{ site.data.krita-brushes[count].videotitle }}</strong></h4>
          </div>
          <div class="card-body">
            {% if site.data.krita-brushes[count].videotype == 'youtube' %}
                 <div class="embed-responsive embed-responsive-16by9">
                   <iframe src="https://www.youtube.com/embed/{{ site.data.krita-brushes[count].videoID }}" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                  </div>
                   {% elsif site.data.krita-brushes[count].videotype == 'vimeo' %}
                  <div class="embed-responsive embed-responsive-16by9">
                   <iframe src="https://player.vimeo.com/video/{{ site.data.krita-brushes[count].videoID }}" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                  </div>
                 {% endif %}
            {% if site.data.krita-brushes[count].videotype == 'image' %}
                   <a href="{{ site.data.krita-brushes[count].image-link }}"><img src="{{ site.data.krita-brushes[count].image-path }}" class="img-fluid" alt="{{ site.data.krita-brushes[count].image-alttext }}"></a>
            {% endif %}
            <h5><br>{{site.data.krita-brushes[count].videodescription }}</h5><br>
            <p><span class="font-weight-bold">Resource type:</span> {{ site.data.krita-brushes[count].resource-type }}</p>
            <p><span class="font-weight-bold">Application tested with:</span> {{ site.data.krita-brushes[count].app-tested }}</p>
            <ul class="list-unstyled mt-3 mb-4">
              <li class="font-weight-bold">download-links:</li>
              {% for entry in site.data.krita-brushes[count].download-links %}
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
