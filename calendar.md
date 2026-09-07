---
layout: default
title: Pack Calendar
---

# Pack 1346 Calendar

Pack events, den meetings, and committee meetings in one place. Tap an event to jump to its details on the [main page](/). To put all of this on your phone, subscribe to the [pack calendar feed](/pack-calendar.ics).

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

## The next 6 weeks


## Week of Monday, September 7

| Date | Time | Event | Where |
|------|------|-------|-------|
| Tuesday, September 8 | 6 PM - 7 PM | [New Parent Information Night](/#new-parent-night) | Fairview Elementary |
| Tuesday, September 8 | 6:30 PM - 7:30 PM | Wolf Den Meeting | Fairview Elementary |
| Sunday, September 13 | 2 PM - 3 PM | Bears/Webelos/AOL: Fairfax County Emergency Operations Center Visit | Ask your den leader |
| Sunday, September 13 | 2 PM - 3 PM | AOL: Fairfax County Emergency Ops Center (EOC) Visit | Ask your den leader |

## Week of Monday, September 14

| Date | Time | Event | Where |
|------|------|-------|-------|
| Tuesday, September 15 | 6:30 PM - 7:30 PM | [September Pack Meeting](/#september-pack-meeting) | Fairview Elementary |

## Week of Monday, September 21

| Date | Time | Event | Where |
|------|------|-------|-------|
| Tuesday, September 22 | 6:30 PM - 7:30 PM | AOL Den Meeting | Fairview Elementary |

## Week of Monday, September 28

| Date | Time | Event | Where |
|------|------|-------|-------|
| Tuesday, September 29 | 6 PM - 7 PM | Lions: Bobcat Adventure | Fairview Elementary (tentative) |

## Week of Monday, October 12

| Date | Time | Event | Where |
|------|------|-------|-------|
| Tuesday, October 13 | 6:30 PM - 7:30 PM | Wolf Den Meeting | Fairview Elementary |
| Tuesday, October 13 | 8 PM - 9 PM | Committee Meeting | Online (video call) |

---

Den meetings are entered by each den's leaders; if your den isn't showing, ask your den leader. Questions about a pack event? Contact Cubmaster Kevin.
