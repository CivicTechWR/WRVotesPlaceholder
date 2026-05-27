---
title: Welcome!
layout: default
---

<section class="flex justify-center">
  <article class="standout-box blue large">
    <div class="big-text header" id="map-box" >
    Election Day is October 26, 2026.
    </div>
  </article>
</section>

We are still deciding whether to run this site for the 2026 municipal
election. Stay tuned!

In the meantime we have gathered some information you might find
useful if you are a potential voter or potential candidate. 

For Voters
------

Learn how to [register to vote], and information about the election. 

You can see official candidate lists on <https://wrvotes.com> . 

For Candidates
----------

Want to run? Here are some resources!




Upcoming Events
---------------

Is there a local election-related event that we have not listed? 
Please email us about it!


{% assign all-events = site.data.sync.events %}
{% assign date-now = site.time | date: "%F" %}


{% assign events-upcoming = all-events
  | where_exp:"ev", "ev.DateTimeStart >= date-now" %}

{% if events-upcoming.size > 0 %}
  <div class="event-wrapper content-box" id="event-wrapper-upcoming">
    {% include list-event-block.html
      event-list=events-upcoming
      header="Upcoming Events"
      teaser-limit=site.teaser_limit_events_generic
      race-id=include.race-id
      big-header=true %}
    </div>
{% else %}
We have no upcoming events to list yet. Contact us if you have some!
{% endif %}



