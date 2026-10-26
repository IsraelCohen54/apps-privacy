# apps-privacy

Public privacy policies for apps published by Israel Cohen, served via GitHub Pages.

This repo is **public on purpose** — GitHub Pages does not serve private repos on the Free
plan, and Google Play requires the privacy policy to be reachable at a public URL by someone
who has *not* installed the app (including the Play reviewer). It contains no app source.

## Layout

One directory per app. Each app's store listing links to **its own page**, never to the
landing page — Play requires the policy at the submitted URL to apply to that specific app,
and an index the reviewer has to navigate is a common rejection cause.

```
index.html                    → landing page (lists the apps)
zmanim-alarm/index.html       → https://israelcohen54.github.io/apps-privacy/zmanim-alarm/
beholy/index.html             → https://israelcohen54.github.io/apps-privacy/beholy/
healthy-reminders/index.html  → https://israelcohen54.github.io/apps-privacy/healthy-reminders/
```

## Adding an app

1. `mkdir <app-slug>` and copy an existing `index.html` as a starting point.
2. **Rewrite the content for that app's real behaviour.** Do not copy claims across apps.
   Zmanim Alarm states that its release build ships with no internet permission at all —
   that is true of *that* app (enforced by `test/assets/offline_invariants_test.dart` in its
   repo) and would be a false statement on a page for an app that does reach the network.
3. Add a link on `index.html`.
4. Update the effective date on any page whose content changed.

## Pages setup

Settings → Pages → Source: **Deploy from a branch** → Branch `main`, folder `/ (root)`.
