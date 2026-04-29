# Month 1 Learning Plan — Privacy Browser Project

## Overview
The goal of this month is to build a mental map of how browsers work, understand fingerprinting deeply, get comfortable with JavaScript browser APIs, and ship your first working Firefox extension.

---

## Week 1 — How Browsers Work

### Concepts
- Read **"How Browsers Work"** by Tali Garsiel (free, just Google it — classic article)
- Watch a YouTube video on the browser rendering pipeline
- Understand the difference between the rendering engine, networking stack, and JavaScript engine

### Hands-On
- Install **Firefox Developer Edition**
- Open DevTools and explore every tab: Network, Console, Storage, Inspector
- Watch a real HTTP request happen in the Network tab when you visit a site

### Goal
Understand what a browser actually does under the hood before writing a single line of code.

---

## Week 2 — Fingerprinting Deep Dive

### Concepts
- Visit **coveryourtracks.eff.org** and read every section carefully
- Read about canvas fingerprinting specifically — understand how a single `<canvas>` element can identify your machine
- Understand the difference between active and passive fingerprinting

### Hands-On
- Visit these sites and document what they collect:
  - amiunique.org
  - browserleaks.com
  - coveryourtracks.eff.org
- Write down every attribute being collected and ask "how would I spoof this?"

### Goal
Know your enemy — fully understand what you're trying to defeat before building defenses.

---

## Week 3 — JavaScript & Browser APIs

### Concepts
- How the DOM works
- Browser APIs: `navigator`, `window`, `screen` objects
- What content scripts are and how they interact with a page

### Hands-On
- Open the browser console and run:
  ```js
  console.log(navigator.userAgent)
  console.log(screen.width, screen.height)
  console.log(Intl.DateTimeFormat().resolvedOptions().timeZone)
  ```
- Try **overriding** them manually in the console
- Read how Brave injects noise into the Canvas API (their GitHub is public)

### Goal
Get comfortable manipulating the exact APIs that fingerprinters exploit.

---

## Week 4 — Build Your First Extension

### Hands-On Only
- Follow Mozilla's **"Your First Extension"** guide (developer.mozilla.org)
- Build an extension that does one thing: logs `navigator.userAgent` to the console
- Then extend it to **override** that value with a generic one
- Test it on browserleaks.com — did it work?

### Deliverable
A working Firefox extension by end of week that overrides at least one fingerprint attribute.

### Goal
Ship something real. Motivation lives in building, not just reading.

---

## End of Month Checkpoint

By the end of Month 1 you should be able to answer:
- [ ] What is the browser rendering pipeline?
- [ ] What attributes make up a browser fingerprint?
- [ ] How does canvas fingerprinting work?
- [ ] How do content scripts interact with a webpage?
- [ ] How do you override a `navigator` property in a Firefox extension?

---

## Resources

| Resource | Link |
|---|---|
| How Browsers Work (Garsiel) | Search "How Browsers Work Tali Garsiel" |
| MDN Web Docs | developer.mozilla.org |
| EFF Cover Your Tracks | coveryourtracks.eff.org |
| Am I Unique | amiunique.org |
| Browser Leaks | browserleaks.com |
| Mozilla Extension Docs | developer.mozilla.org/en-US/docs/Mozilla/Add-ons |
| Brave GitHub | github.com/brave/brave-browser |