# How to Set Up the Live Calendar on oplo.gold

The schedule on oplo.gold shows TWO things stacked:

1. **TOP — Live Google Calendar** (a Google Calendar embed showing all your real upcoming events)
2. **BOTTOM — Featured Upcoming Sessions** (the 6 hand-styled cards we built — these stay as a backup and to highlight key sessions)

This guide explains how to wire YOUR Google Calendar to the embed at the top.

---

## ONE-TIME SETUP (10 minutes)

### Step 1 — Create a dedicated OPLO calendar in Google Calendar

If you already have an OPLO calendar in Google Calendar, skip to Step 2.

1. Open https://calendar.google.com on your computer
2. In the left sidebar, find **"Other calendars"** and click the **+** next to it
3. Click **"Create new calendar"**
4. Name: `OPLO Training Schedule`
5. Time zone: Central Time (Houston, TX)
6. Click **Create calendar**

### Step 2 — Make the calendar public

This is required for the website to read it. **Important:** only the events you add to THIS specific calendar will become public — your other personal calendars stay private.

1. Back in Google Calendar's left sidebar, find your `OPLO Training Schedule` calendar
2. Hover over it → click the **⋮** (three dots) → **Settings and sharing**
3. Scroll down to **"Access permissions for events"**
4. Check the box: **"Make available to public"**
5. The dropdown next to it should be set to **"See all event details"**
6. A popup may warn you the calendar is becoming public — confirm

### Step 3 — Grab your Calendar ID

1. Still on the calendar settings page, scroll down to **"Integrate calendar"**
2. Find the field labeled **"Calendar ID"** — it's a long string like:
   `abc1234567890abcdef@group.calendar.google.com`
3. Copy that entire Calendar ID

### Step 4 — Paste it into index.html

1. Go to https://github.com/joseruddy77-web/oplo-gold-site → click `index.html` → pencil icon (edit)
2. Press **Ctrl+F** (Cmd+F on Mac), search for `YOUR_CALENDAR_ID_HERE`
3. Replace it with your Calendar ID, but with `@` changed to `%40`
   - Example: `abc1234567890abcdef%40group.calendar.google.com`
4. Commit the change
5. Wait ~60 seconds, refresh oplo.gold — your live calendar appears

---

## Daily use — adding/editing events

Once it's set up, you NEVER edit the website again. Just use Google Calendar normally:

- **Add an event** in Google Calendar → it shows on oplo.gold within minutes
- **Edit/delete an event** in Google Calendar → website updates automatically
- **Update on your phone** via the Google Calendar app → still works
- **Invite/share with staff** so they can also add events to this calendar

---

## What if I want to disable the live calendar?

Easy. In `index.html`, find the `<div class="gcal-wrap">` block and either delete it entirely, or wrap it in HTML comments `<!-- ... -->`. The featured cards section below it will continue to work on its own.

---

## The Featured Cards (bottom section)

The 6 styled cards below the live calendar are STILL editable as before. They're useful for:
- Highlighting your most important upcoming sessions with extra detail
- Acting as a fallback if Google Calendar fails to load
- Curating "must-see" sessions even if your full calendar is busy

To edit them: find `<!-- CARD 1 -->` in `index.html` and update the date/course/seats text directly.

---

## Troubleshooting

**The calendar shows "This calendar can't be embedded" or is blank:**
- The calendar isn't set to public yet. Go back to Step 2.

**The calendar shows events but is cut off:**
- The iframe is 640px tall on desktop, 460px on mobile. If you have many events per day, consider switching the URL parameter `mode=MONTH` to `mode=AGENDA` for a list-style view.

**I want a different default view:**
- In the iframe `src` URL, change `mode=MONTH` to one of: `WEEK`, `AGENDA`, `MONTH`

**Calendar looks too bright:**
- We applied a `filter: invert + hue-rotate` to make Google's white calendar fit the dark theme. If you don't like how it looks, find `.gcal-frame iframe` in the CSS and remove or adjust the `filter:` line.

---

## Privacy note

Making the OPLO calendar public means:
- ✅ Visitors to oplo.gold can see event titles, dates, times, descriptions
- ❌ They cannot see your other personal Google Calendars
- ❌ They cannot add, edit, or delete anything
- ❌ They cannot see who the calendar belongs to (just the public event data)

If you accidentally added a personal event to the wrong calendar, it'll be visible to the public until you move or delete it. As a habit, keep this calendar **OPLO classes only**.
