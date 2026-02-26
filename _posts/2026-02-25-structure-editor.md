---
layout: post
title: "A Better Structure Editor"
description: "A new non-destructive structure editor for faster and easier building creation"
categories: [Destruction system]
tags: [GameDev, C#, Tools]
date: 2026-02-25
---

{% include embed/youtube.html id="KoEW-fWakx4" %}

> Skip to 6:23 to see the final result.
{: .prompt-tip }

Here's a demo of an idea I had for a better structure editor. It takes out a lot of the manual work of setting links. Making a building is a few simple steps:

1. Put down foundations/anchors where the building meets the ground.
2. Draw your beams and supports.
3. Generate walls & floors between several beams.
4. Cut holes in surfaces for doors, windows, ladders, stairs, etc.

The editor automatically handles fracturing the walls & floors and generates links between all their pieces and the beams they're connected to. The nice thing too is that the cuts for doors and windows are non-destructive. They can be undone or edited (forgot to show that in the video).

I haven't made any videos of the old editor. But basically you had to manually link many pieces. There were helpers for generating walls, floors, and pillars, but it was up to you to link dozens of pieces together when joining those elements to each other. Making doors and windows meant manually selecting every piece in the cut and deleting them.

I tried to add voronoi fracturing to have more realistic looking broken pieces for materials like concrete. It was still very buggy so I didn't include it here.

## Future Improvements

There are a lot of improvements that can be made to this editor still:

- **Non right angle beams and walls** -- Support for angled beams and walls so buildings aren't limited to right angles.
- **Arbitrary mesh import** -- The ability to input arbitrary meshes, link them to the structure, and fracture them. The buildings will look boring if they're all right angles. Also, some decorations like signs are easier to make in an external tool like Blender, then import.
- **More beam material options** -- For example, multi-material beams with a steel core surrounded by concrete.
- **Stair and ladder generation** -- Tools for generating stairs and ladders.
- **Mirroring/symmetry** -- A mirroring/symmetry feature to speed up building creation.
- **Better visual indicators** -- For example, if you're drawing a beam and your endpoint is parallel with another beam on the same axis, it should draw a dashed line between them so you know they're parallel.

## Cleanup

I need to take some time to clean up the code for this editor. I made it quick and dirty since I wasn't sure if the idea would work. I'm satisfied with the result. It lets me make new structures quicker and easier. Need to add more features and fix the lag.
