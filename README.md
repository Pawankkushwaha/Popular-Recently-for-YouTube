# Popular Recently for YouTube

A Chrome extension that shows creators what's actually popular *recently* on any YouTube channel videos, its Shorts, not just its all-time greatest hits, and turns that data into research an AI tool can use. 

## Try it

- **Chrome Web Store:** link coming soon. 
- **Website:** https://popularrecently.netlify.app

## The problem

YouTube's own "Popular" sort is all-time only. For a channel that's been active for years, that view is dominated by old viral hits and tells you nothing about what's actually resonating with audiences right now. For research and content planning, that's the wrong signal.

## What it does

Popular Recently re-sorts a channel's real video grid (Videos tab or Shorts tab) by view count within a time window you choose, from 1 month up to all-time, directly inside YouTube's own page. It also scans a channel, a single video, or a whole playlist and exports the real data (views, dates, likes, transcripts, thumbnails) so you can study it or hand it to an AI tool. No login, no YouTube Data API key, ever.

## Features (How it help content creators)

**Sorting and filtering**
- A native-style "Popular recently" chip sits right next to YouTube's own Latest / Popular / Oldest chips and re-sorts the real video grid in place, on both a channel's Videos tab and its Shorts tab
- Time window selector: 1 / 3 / 6 / 12 / 24 months, or all-time
- A resizable side panel (from the toolbar icon) lists the same results with thumbnails, titles, direct links, and duration badges, and remembers your last scan so reopening it doesn't rescan
- VidIQ's views-per-hour and outlier-score chips are picked up and shown alongside each result, when VidIQ is installed and has scored that video

**Selecting and exporting**
- Per-row checkboxes, a select-all checkbox, and click-drag multi-select across rows
- **Channel scan export** — select any number of videos and download exactly two files: a combined info file (views, upload date, like count, URL for every selected video) and a combined thumbnails PDF (a labeled grid with a views/age line under each title)
- **Single-video export** — from any video's own watch page, download that video's title, exact views, upload date, like count, comment count, URL, thumbnail, and its **full timed transcript**, as two plain files
- **Playlist export** — from any playlist page, export the entire playlist's data in the same combined-file format, no selection step, no size limit
- The thumbnails PDF carries an invisible, real text layer under each image (title, views, age, date, likes, URL), so tools that only read text, like NotebookLM, can actually index it, not just the picture

**Built to hold up on real, huge channels**
- Shorts have no visible upload date anywhere on the page, so the extension fetches real dates directly rather than relying on what's on-screen
- A Stop button cancels a long scan early and shows a clearly marked partial result
- A channel's Shorts data is scanned once and shared between the chip and the panel, so switching the time window or reopening the panel doesn't rescan from zero
- Survives YouTube's own single-page-app navigation (switching tabs without a full reload) and its periodic changes to page markup and label formats, both of which broke earlier versions in real use and were fixed

## How it helps creators

- **Competitor research** — see what a channel is actually landing recently, not what went viral three years ago
- **Content planning** — spot the recent topics and formats getting outsized views (and VidIQ's outlier score, where available) to inform your next video or Short
- **Reverse-engineer any channel's content strategy, for free** — export a channel's, a video's, or a playlist's real performance data and feed it straight into an AI tool like Claude, ChatGPT, or NotebookLM. Ask it what topics, formats, hooks, and patterns are actually working for that channel right now, and use that to plan your own next video, using the same real data the creator themselves would look at
- **Building a swipe file** — a library of exported titles, thumbnails, view counts, and transcripts for the videos worth studying

## What's next

- An inline time-window menu directly on the chip, instead of the separate status strip
- Broader platform coverage beyond YouTube (Instagram is on the roadmap)
- Continued reliability work as YouTube's own page keeps changing underneath it

This is an actively developed project. Features above reflect the most advanced build; new ones ship to the Chrome Web Store as they're ready (see **Try it** below for what's live right now).

## What building this involved

- **Researching a real problem, not a hypothetical brief.** I hit this exact limitation using YouTube myself, then defined what an actual fix would need to do.
- **Shipping a working version first, then iterating on real usage.** Every feature above, the in-grid chip, the export formats, Shorts and playlist support, was added because of how the tool was actually being used, not planned upfront.
- **Debugging real breakage as the target platform changed underneath it.** YouTube's page markup, label formats, and scroll/interaction behavior shifted several times during development; each break had to be diagnosed from scratch and fixed without regressing what already worked.
- **Taking it from working prototype to an actual public release.** That meant a Chrome Web Store submission, a privacy policy and support pages, and a companion website, not just code that runs locally.
- **Making deliberate scope calls under a real constraint.** I chose to submit a simpler, lower-risk build first rather than wait for every feature above to be ready, and I'm shipping the rest as updates.

This loop, spotting a real problem, building a fix, and living with (and fixing) what breaks, is the kind of ownership I look for chances to practice: the skill set behind an Associate Product Manager, Product Manager, or an early co-founder / founder's-office seat at a startup.

## Built with

Manifest V3 Chrome extension, content-script based (no API key or login needed). Vibe-coded end to end with [Claude Code](https://claude.com/claude-code) as a hands-on build to learn AI-assisted development.


## About this repo

This repository is a project showcase, not the source code. It exists to document and share what the extension does without publishing the codebase itself.
