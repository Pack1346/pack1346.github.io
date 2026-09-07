---
layout: default
title: Pack Calendar
---

# Pack 1346 Calendar

Pack events, den meetings, and committee meetings in one view. Click any event for the when and where; pack events link through to details on the [main page](/). To put all of this on your phone, subscribe to the [pack calendar feed](/pack-calendar.ics).

*Last updated: September 7, 2026*

<div id="pack-calendar" style="margin:1em 0 2em 0;"></div>
<div id="pack-event" style="display:none;position:fixed;inset:0;background:rgba(0,0,0,.35);z-index:1000;align-items:center;justify-content:center;padding:1rem;">
  <div style="background:#fff;color:#222;border-radius:8px;padding:1.25rem 1.5rem;max-width:22rem;width:100%;box-shadow:0 8px 30px rgba(0,0,0,.25);">
    <h3 id="pe-title" style="margin:0 0 .5rem;font-size:1.15rem;color:#222;"></h3>
    <p id="pe-when" style="margin:.25rem 0;"></p>
    <p id="pe-where" style="margin:.25rem 0;"></p>
    <p id="pe-link" style="margin:.75rem 0 0;"></p>
    <p style="margin:1rem 0 0;text-align:right;"><button id="pe-close" type="button" style="padding:.35rem .9rem;">Close</button></p>
  </div>
</div>
<script src="https://cdn.jsdelivr.net/npm/ical.js@1.5.0/build/ical.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.15/index.global.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@fullcalendar/icalendar@6.1.15/index.global.min.js"></script>
<script>
(function ready(fn) { document.readyState === 'loading' ? document.addEventListener('DOMContentLoaded', fn) : fn(); })(function () {
  var box = document.getElementById('pack-event');
  function hide() { box.style.display = 'none'; }
  document.getElementById('pe-close').addEventListener('click', hide);
  box.addEventListener('click', function (e) { if (e.target === box) hide(); });
  document.addEventListener('keydown', function (e) { if (e.key === 'Escape') hide(); });
  function fmtTime(d) { return d.toLocaleTimeString([], { hour: 'numeric', minute: '2-digit' }); }
  function show(ev) {
    var day = ev.start.toLocaleDateString([], { weekday: 'long', month: 'long', day: 'numeric' });
    var when = ev.allDay ? day + ', all day' : day + ', ' + fmtTime(ev.start) + (ev.end ? ' to ' + fmtTime(ev.end) : '');
    document.getElementById('pe-title').textContent = ev.title;
    document.getElementById('pe-when').textContent = when;
    document.getElementById('pe-where').textContent = ev.extendedProps.location ? 'Where: ' + ev.extendedProps.location : '';
    var link = document.getElementById('pe-link'); link.innerHTML = '';
    if (ev.url) { var a = document.createElement('a'); a.href = ev.url; a.textContent = 'Details on the main page'; link.appendChild(a); }
    box.style.display = 'flex';
  }
  var cal = new FullCalendar.Calendar(document.getElementById('pack-calendar'), {
    initialView: 'dayGridMonth',
    headerToolbar: { left: 'prev,next today', center: 'title', right: 'dayGridMonth,listMonth' },
    events: { url: '/pack-calendar.ics', format: 'ics' },
    eventTimeFormat: { hour: 'numeric', minute: '2-digit', meridiem: 'short' },
    height: 'auto',
    dayMaxEvents: 3,
    eventClick: function (info) { info.jsEvent.preventDefault(); show(info.event); }
  });
  cal.render();
});
</script>

<noscript>This calendar needs JavaScript. Subscribe to the <a href="/pack-calendar.ics">feed</a> instead, or see the events list on the <a href="/">main page</a>.</noscript>

---

Den meetings are entered by each den's leaders; if your den isn't showing, ask your den leader. Questions about a pack event? Contact Cubmaster Kevin.
