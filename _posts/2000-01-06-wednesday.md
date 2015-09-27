---
title: "Quarta 14"
bg: '#4f7c80'
color: black
border-color: white
fa-icon: battery-half
---

<div class="section-lines section-top section-left"></div>
{% for activity in site.data.agenda.wednesday %}
  {% capture thecycle %}{% cycle 'even', 'odd' %}{% endcapture %}
  {% if thecycle == 'odd' %}
  {% if activity == site.data.agenda.wednesday.last %}
  <div class="activity section-left">
  {% else %}
  <div class="activity section-left section-bottom">
  {% endif %}
    <div class="row activity-info-wrapper valign-wrapper">
      <div class="col m3 activity-img valign">
        <img  src="img/{{ activity.image }}" alt="{{ activity.title }}">
      </div>
      <div class="col m9 activity-info">
        <h4 class="activity-title"> {{ activity.title }} </h4>
        <div class="col s12 activity-time">
          <i class="fa fa-clock-o"></i> <span> {{ activity.time }} </span>
        </div>
        <div class="col s12 activity-place">
          <i class="fa fa-map-marker"></i> <span> {{ activity.place }} </span>
        </div>
        <p class="col m12 activity-desc"> {{ activity.text }} </p>
      </div>
    </div>
  </div>
  {% else %}
  {% if activity == site.data.agenda.wednesday.last %}
  <div class="activity section-right">
  {% else %}
  <div class="activity section-right section-bottom">
  {% endif %}
    <div class="row activity-info-wrapper valign-wrapper">
      <div class="col m9 activity-info">
        <h4 class="activity-title"> {{ activity.title }} </h4>
        <div class="col s12 activity-time">
          <i class="fa fa-clock-o"></i> <span> {{ activity.time }} </span>
        </div>
        <div class="col s12 activity-place">
          <i class="fa fa-map-marker"></i> <span> {{ activity.place }} </span>
        </div>
        <p class="col m12 activity-desc"> {{ activity.text }} </p>
      </div>
      <div class="col m3 activity-img valign">
        <img  src="img/{{ activity.image }}" alt="{{activity.title}}">
      </div>
    </div>
  </div>
  {% endif %}
{% endfor %}
{% if thecycle == 'even' %}
<div class="section-lines section-bottom section-left"></div>
  {% else %}
<div class="section-lines section-bottom section-right"></div>
{% endif %}
