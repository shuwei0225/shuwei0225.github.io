---
layout: essay
type: essay
title: "Final Project Proposal"
date: 2025-11-04
labels:
  - Software Engineering
  - Nextjs
---

# Mānoa Hunting — A personalized guide to good restaurants around UH

## Overview

### The problem
UH Mānoa students, staff, and neighbors are surrounded by great food—but discovering the **right** spot at the **right** time is hard. Instagram is noisy, Google Maps is generic, and group chats get outdated. We need a way to filter by **budget**, **dietary needs**, **distance/wait time**, **parking/bus access**, and even **campus schedule** (class blocks, club meetings, labs).

### The solution
**Mānoa Hunting** is a Next.js + React + Bootstrap 5 web app that builds a **personal taste profile** for each logged-in user and recommends nearby restaurants and food trucks around UH Mānoa (and greater Oʻahu) with **live crowd-sourced “vibes”** (busy/quiet), **today’s specials**, **student deals**, and **time-to-eat** suggestions between classes.

Our “special sauce”: after registration, users answer a short taste quiz (price comfort zone, diet, spice tolerance, allergens, cuisines, caffeine needs, time windows). The app learns from their bookmarks, ratings, and “nope” list to deliver **hyper-personalized** picks and smart notifications (e.g., “You’ve got 55 minutes before ICS 314 — two top picks within a 6-minute walk, average wait 8 minutes.”).

**Tech & hosting**: Next.js (App Router), React, Bootstrap 5 UI, MongoDB (profiles, places, reviews), NextAuth (email or UH Google SSO), Map/Geolocation APIs for distance & routing, CI/CD from **GitHub** (public repo; docs via GitHub Pages; deployment from GitHub to Vercel).

---

## Names of the proposers
- **Shuwei Chen**

---

## Mockup page ideas

1. **Landing Page**
   - Hero: “Find your next bite near UH.”
   - Quick filters: Budget ($/$$/$$$), Distance (walk/BIKESHARE/bus), Diet (vegetarian, vegan, halal, gluten-free), Vibe (quiet to study, lively with friends).
   - “Sign in to personalize” CTA.

2. **Discover (Personalized Feed)**
   - Card grid of nearby restaurants ranked by your taste profile.
   - Chips showing *fit reasons* (e.g., “close to POST,” “spicy level 2,” “under $12,” “open now”).
   - Live “vibe meter” (crowd-sourced check-ins + historical patterns).

3. **Map View**
   - Map with pins, walking times from your current building (e.g., POST, Hamilton, Campus Center).
   - Toggle: “Between classes” (shows only places that fit your available window).

4. **Place Details**
   - Menu highlights, dietary flags, student deals, today’s specials, average wait, parking & bus notes (routes 4/13/6…), user photos.
   - Buttons: “Add to Favorites,” “I’m Here,” “Queue vibes: Busy/Chill.”

5. **My Profile**
   - Taste quiz (cuisines, spice, allergens, price), saved places, hidden places, notification windows (e.g., weekdays 11:00–14:00).
   - “Taste Twin” section: people with similar palates (anonymized) and what they loved this week.

6. **Admin Dashboard**
   - Verify businesses, moderate photos/reviews, manage specials & tags, merge duplicates.

---

## Use case ideas

- **New user → first lunch**
  1. User hits Landing, signs in.
  2. Completes 1-minute taste quiz; grants geolocation.
  3. Discover shows 8 nearby cards tailored to budget + diet; “Between classes: 55 minutes” filter on by default.
  4. User opens Place Details → sees “average wait 7–10 min,” “$11 lunch special,” “5-minute walk from POST.”
  5. User bookmarks, walks using Map View, taps “I’m Here,” and later rates + flags favorites.

- **Commuter with dietary restriction**
  1. Profile set to gluten-free and halal preferred.
  2. Discover prioritizes compliant menus and shows “trust score” based on community tags/photos.
  3. User subscribes to notifications 10:30–12:30 on Tue/Thu; receives ping when a compliant place near Campus Center is calm.

---

## Beyond the basics

- **Crowd-sourced Vibe & Wait Time**
  Lightweight check-ins (“Chill / Normal / Busy”), auto-expires. Historical smoothing predicts lunch rush near class transition times.

- **Smart Time Windows**
  Parse your *optional* class schedule blocks (or manual time windows) to suggest places that fit your precise gaps, including walk time + queue + eat time.

- **Transit & Parking Hints**
  Quick view: bus lines, bike racks, meter/lot notes, and known “gotchas” (cash-only windows, last call times).

- **Student Deals & Loyalty**
  Owners can post UH-specific specials; users can track stamp/punch progress (QR or one-tap “redeemed”), with guardrails to prevent abuse.

- **Evaluation plan (local community)**
  Recruit UH students (ICS 314 classmates, clubs) and nearby vendors on University Ave/King St to test recommendations, vibe accuracy, and deal redemption. Gather usability metrics and iterate.

---

## Approach

- **Stack**: Next.js (App Router), React, Bootstrap 5 components, MongoDB Atlas, NextAuth, Map & Geolocation APIs.
- **Data model**: `User`, `TasteProfile`, `Place`, `MenuItem`, `Special`, `CheckIn`, `Review`, `Favorite`.
- **Special sauce state**: Per-user taste vectors, favorites/hidden, notification windows, class-gap windows, and “Taste Twin” cohorts.
- **DevOps**: Public **GitHub** repo with Issues/Projects, ESLint/Prettier, GitHub Actions CI, preview deploys; app deployed from GitHub to Vercel; portfolio essay published via **GitHub Pages** (TechFolio).
- **Testing**: Playwright for E2E (critical paths: sign-in, discovery, place details, check-ins), Jest/RTL for components, seed data for local dev.

---
