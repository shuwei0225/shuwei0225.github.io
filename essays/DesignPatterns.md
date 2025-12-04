---
layout: essay
type: essay
title: "Reflecting on Design Patterns in Run & Route Hub"
date: 2025-12-02
published: true
labels:
  - Engineering
---

<img width="200px" class="rounded float-start pe-4" src="../img/design-patterns.png">

*Design patterns: reusable solutions that shape code the way architectural blueprints shape buildings.*

## The Invisible Structure Behind Good Software

When I first heard the phrase *design patterns*, it sounded abstract—like something meant for big tech companies or senior engineers with decades of experience. But as we built **Run & Route Hub**, our ICS 314 final project, I realized design patterns are much more down-to-earth. They’re like the silent structure behind the code, the techniques developers reuse the same way chefs reuse cooking methods or musicians reuse chord progressions.  

Instead of reinventing a new solution every time, patterns give you a familiar shape to build from. And once you start spotting them, it’s impossible to unsee them—they show up everywhere in real software.

## Patterns That Emerged in Our Project

A pattern we encountered constantly was the **Component pattern**, something built right into React. Every card, every form, every dashboard panel becomes a small, reusable unit—a predictable piece of UI that behaves consistently. Instead of duplicating markup for runner profiles or route previews, we built components once and reused them like well-designed Lego bricks. This is one of those patterns you use without even realizing it until you step back and look at the bigger picture.

Another pattern appeared in our project’s database structure: the **Singleton pattern**. Collections like `Users`, `Routes`, and `BuddyPreferences` behave as single, globally accessible instances. No matter where we import them, they all point to the same shared data source. It’s like having one central pantry in a kitchen—every team member grabs ingredients from the same place, so everything stays consistent.

Meteor’s reactivity naturally nudged us into the **Observer pattern**. When a user signs in or updates their settings, multiple parts of the site automatically react—navbars update, buddy filters refresh, and dashboards re-render. Instead of manually notifying each component, the reactive data source acts like a signal system in the background, quietly keeping everything synchronized.

We even used a simplified version of the **Strategy pattern** when dealing with map-related behaviors. Whether we displayed a polyline, calculated distances, or showed markers, each operation followed the same interface—different strategies, same plug-and-play structure. Being able to swap behaviors without rewriting the whole function made our code far easier to maintain.

## Why These Patterns Matter

Before this project, I saw patterns as something you *look up*. Now I see them as something you naturally *grow into*. We didn’t intentionally sit down and say, “Let’s implement the Observer pattern”—we simply solved problems in ways that ended up matching these classic structures.

And that’s the beauty of design patterns: they’re not rules you must memorize, they’re solutions you slowly recognize as your experience grows.  

By the time we finished Run & Route Hub, I realized that if an interviewer asked me, “What are design patterns, and which ones have you used?” I finally have a real answer:

> Design patterns are reusable techniques for solving common problems, and in our final project we used them everywhere—React components, Meteor’s reactivity, our database collections, and even how we handled maps. They made the project cleaner, more maintainable, and easier for five different people to build together.

## Team Members
Chen, Shuwei  
Chen, Renjie  
Hatanaka, Jacob  
Scales, Albert  
Woo, Preston
