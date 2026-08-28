# ASCEND: Iron Path

A mobile-first, installable, offline-capable fitness PWA built around the 12-week dumbbell + bodyweight + bicycle/glider routine.

## What is included
- 12-week phased strength/cardio schedule
- Workout A/B exercise logging
- Per-set weight, reps/time and RIR tracking
- Automatic rest timer with sound/vibration cues
- XP, levels, ranks, weekly quests and achievements
- Cardio tracker using an easy/moderate/hard talk-test model
- Weight / waist / hips / chest check-ins and trend graph
- Calendar export for 12 weeks of native phone reminders
- Browser notification permission + test notifications
- Local-only data storage, JSON backup/import
- PWA manifest, offline service worker and install prompt
- Responsive phone / tablet / desktop layout
- Accessibility support for reduced motion

## Important notification limitation
This build is intentionally server-free. Browser notifications can be shown through the service worker, but a purely static PWA cannot reliably wake itself at an exact future time on every mobile browser. Periodic Background Sync is not broadly supported. The **Export 12-week calendar** button therefore creates native calendar reminders, which are the dependable no-server route.

For a future native Android/iOS build, package the app with Capacitor and use the platform local-notifications plugin for guaranteed scheduled alarms.

## Run locally
Service workers require HTTP/HTTPS rather than opening `index.html` directly.

From this folder:

```bash
python -m http.server 8080
```

Then open `http://localhost:8080`.

For phone use, deploy the folder to GitHub Pages, Netlify, Cloudflare Pages or another HTTPS static host and use **Add to Home Screen / Install App**.

## Research basis used for product decisions
- ACSM (2026): consistency, all major muscle groups, progressive resistance training, home/bodyweight training can be effective.
- WHO: adults should work toward 150–300 min/week moderate aerobic activity plus muscle strengthening on 2+ days/week.
- Gamification evidence: systematic reviews show small improvements in physical activity/adiposity outcomes; rewards are therefore used to support adherence, not presented as a fat-loss mechanism.
- mHealth adherence reviews: personalization, tracking, goal setting, user-friendly design and individualized reminders are recurring adherence-support features.

## Design reference note
Current fitness-app UI concepts were reviewed for information hierarchy and gamified dashboards. The shipped interface does not copy those assets; it uses original CSS/SVG-style visuals so it remains lightweight and offline-friendly.

## Safety
This is a workout tracker, not medical advice or a medical device. The program intentionally starts conservatively and avoids 1-rep-max testing, daily HIIT and punitive missed-day mechanics.
