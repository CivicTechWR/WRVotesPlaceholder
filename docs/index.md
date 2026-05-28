---
title: Welcome!
layout: default
---

<h1 id="map-box" > Municipal Election Day is Oct 26, 2026.</h1>

We are still deciding whether to run this site for the 2026 municipal
election. Stay tuned! 

In the meantime we have gathered some information you might find
useful if you are a potential voter or potential candidate. 

Get Informed for the Upcoming Election
------

Check out these resources about the upcoming election: 

- Learn how to [register to vote](resources/amend-voters-list).
- Learn more [about the 2026 election](resources/voter-info).
- See official candidate lists from the official municipal sites
  linked from <a href="https://wrvotes.com"
  target="_blank">https://wrvotes.com</a>.


Planning to Run as a Candidate?
----------

Are you thinking of running for office? Great!

The deadline to register a candidate nomination is **August 21, 2026**. 

The Region of Waterloo has published an [overview of the nomination
process](https://www.regionofwaterloo.ca/government-and-council/elections/#Summaryofthenominationprocess).

The Association of Municipalities of Ontario has a [comprehensive
municipal election
page](https://www.amo.on.ca/about-us/municipal-101/municipal-elections),
and a resource library containing [Supports for
Candidates](https://ldsb-dogwood.softr.app/candidatesupports).



{% assign all-events = site.data.sync.events %}
{% assign date-now = site.time | date: "%F" %}


{% assign events-upcoming = all-events
  | where_exp:"ev", "ev.DateTimeStart >= date-now" %}

{% if events-upcoming.size > 0 %}
  <div class="" id="event-wrapper-upcoming">
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

Is there a local election-related event that we have not listed? 
Please email us about it at <civictechwr.wrvotes@gmail.com>!


