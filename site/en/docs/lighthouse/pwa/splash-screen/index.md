---
layout: 'layouts/doc-post.njk'
title: Is not configured for a custom splash screen
description: |
  Learn how to create a custom splash screen for your Progressive Web App.
date: 2019-05-04
updated: 2019-09-19
---

A custom splash screen makes your [Progressive Web App (PWA)](https://web.dev/progressive-web-apps/#make-it-installable) feel more like an
app built for that device. By default, when a user launches your PWA from the home screen,
Android displays a white screen until the PWA is ready.
The user may see this blank, white screen for up to 200&nbsp;ms.
By setting up a custom splash screen,
you can show your users a custom background color and your PWA's icon,
providing a branded, engaging experience.

## How the Lighthouse splash screen audit fails

[Lighthouse](/docs/lighthouse/overview/)
flags pages that don't have a custom splash screen:

<figure>
  {% Img src="image/tcFciHGuF3MxnTr1y5ue01OGLBn2/CKrrTDSCZ0XLZ7ABKlZt.png", alt="Lighthouse audit showing site isn't configured for a custom splash screen", width="800", height="98" %}
</figure>

{% Partial 'lighthouse-pwa/scoring.njk' %}

## How to create a custom splash screen

Chrome for Android automatically shows your custom splash screen as long as
you meet the following requirements in your [web app manifest](https://web.dev/add-manifest/):

- The `name` property is set to the name of your PWA.
- The `background_color` property is set to a valid CSS color value.
- The `icons` array specifies an icon that is at least 512x512&nbsp;px.
- The specified icon exists and is a PNG.

See [Adding a Splash Screen for Installed Web Apps in Chrome 47](https://web.dev/add-manifest/#splash-screen)
for more information.

{% Aside %}
While Lighthouse's audit will pass when a single 512x512&nbsp;px icon is present,
there is some disagreement about what icons a PWA should include.
See [Audit: icon size coverage](https://github.com/GoogleChrome/lighthouse/issues/291)
for a discussion about the pros and cons of different approaches.
{% endAside %}

## Resources

[Source code for **Is not configured for a custom splash screen** audit](https://github.com/GoogleChrome/lighthouse/blob/master/lighthouse-core/audits/splash-screen.js)
