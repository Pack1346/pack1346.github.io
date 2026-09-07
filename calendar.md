---
layout: default
title: Pack Calendar
---

# Pack 1346 Calendar

Pack events, den meetings, and committee meetings in one view. Click a pack event to jump to its details on the [main page](/). To put all of this on your phone, subscribe to the [pack calendar feed](/pack-calendar.ics).

*Last updated: September 7, 2026*

<div id="pack-calendar" style="margin:1em 0 2em 0;"></div>
<script src="https://cdn.jsdelivr.net/npm/ical.js@1.5.0/build/ical.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.15/index.global.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@fullcalendar/icalendar@6.1.15/index.global.min.js"></script>
<script>
document.addEventListener('DOMContentLoaded', function () {
  var el = document.getElementById('pack-calendar');
  var narrow = window.matchMedia('(max-width: 640px)').matches;
  var cal = new FullCalendar.Calendar(el, {
    initialView: narrow ? 'listMonth' : 'dayGridMonth',
    headerToolbar: { left: 'prev,next today', center: 'title', right: 'dayGridMonth,listMonth' },
    events: { url: '/pack-calendar.ics', format: 'ics' },
    eventTimeFormat: { hour: 'numeric', minute: '2-digit', meridiem: 'short' },
    height: 'auto',
    dayMaxEvents: 3,
    eventClick: function (info) {
      if (info.event.url) { info.jsEvent.preventDefault(); window.location = info.event.url; }
    }
  });
  cal.render();
});
</script>

<noscript>This calendar needs JavaScript. Subscribe to the <a href="/pack-calendar.ics">feed</a> instead, or see the events list on the <a href="/">main page</a>.</noscript>

---

Den meetings are entered by each den's leaders; if your den isn't showing, ask your den leader. Questions about a pack event? Contact Cubmaster Kevin.
