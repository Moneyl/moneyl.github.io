---
layout: post
title: "Destruction System Update #1"
description: "Dust effects, collision damage, stress improvements, and sound effects"
categories: [Destruction system]
tags: [GameDev, C#]
date: 2026-02-23
---

{% include embed/youtube.html id="XMFg2D9_AYk" %}

## Improvements

I've made a few improvements to the destruction:

- **Dust effects** — Added various dust effects when pieces get destroyed in an explosion or from colliding with another object.
- **Collision damage** — Collisions with other objects can damage structures now.
- **Weight based stress** — Objects resting on or rolling over structures have their weight applied to the stress system. This means heavy objects on top of a structure could make it collapse (like a tank driving over a damaged bridge). I'll need to make another video to demo this properly.
- **Sound effects** — Added sound effects for impacts and destruction. I'm not completely satisfied with the sounds I chose, but it's an improvement. I also need to tweak the volume falloff settings. It gets quiet too quickly with distance.

## Next Steps

- **Improve the structure designer** — Right now making buildings is a very slow and time consuming process. I have an idea for a different kind of editor that I think will speed things up significantly using non-destructive editing methods. So, for example, you could add/remove/move/resize windows, doors, and other features on walls without having to recreate the whole wall or cut the hole out manually.
- **More interesting buildings** — Make buildings with multiple floors, multiple types of materials, and features like doors, windows, stairs, etc.
- **Tweak the stress system** — The stress system doesn't work quite like I want it to yet. I need to test it more thoroughly and make sure it works as expected. Part of the problem is learning how to design buildings that are satisfying to destroy. The ones I've built so far are way too strong and can stay standing with one support beam left. Its a careful balance.
- **Push structure sizes to the limit** — See how big I can go while having reasonable performance. Stress runs on background threads, so I suspect any lag would be from too many things breaking at once or too many physics bodies being active at once. The latter could be helped by setting a rubble limit and culling pieces over the limit.
