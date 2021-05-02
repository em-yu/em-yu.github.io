---
title: "CASSIE: Curve And Surface Sketching in Immersive Environments"
date: 2021-02-01T14:26:10+01:00
journal: "2021, ACM Conference on Human Factors in Computing Systems (CHI)"
authors:
    - 
        name: "Emilie Yu"
        url: "em-yu.github.io"
    - 
        name: "Rahul Arora"
        url: "http://www.dgp.toronto.edu/~arorar/en/"
    - 
        name: "Tibor Stanko"
        url: "https://tiborstanko.sk/"
    - 
        name: "J. Andreas Bærentzen"
        url: "http://people.compute.dtu.dk/janba/"
    -
        name: "Karan Singh"
        url: "http://www.dgp.toronto.edu/~karan/"
    -
        name: "Adrien Bousseau"
        url: "http://www-sop.inria.fr/members/Adrien.Bousseau/"
teaser: "CASSIE_teaser.jpg"
bigTeaser: "figures/CASSIE/CASSIE_big_teaser.png"
bigTeaserCaption: "Freehand 3D sketching in AR/VR allows rapid conceptualization of design ideas (a). However, 3D inputs are prone to
large inaccuracies (a, inset) and sketches cannot be utilized in downstream design pipelines. Our novel 3D sketching system,
CASSIE, allows the creation of clean, well-connected 3D curve networks by performing automatic stroke neatening (b). These
curve networks are augmented by our on-the-fly cycle detection and surfacing method (c) which improves shape perception by
providing occlusion cues. We evaluated CASSIE with 12 users and utilized it for creating 3D concepts for a variety of application
domains (d)."
summary: "
    We prototype a 3D sketching interface in VR, where the user's strokes are automatically neatened to form a well-connected curve network. We additionnaly infer and create surface patches on the sketch, making it possible to create a 3D surface from a few 3D brush strokes.
"
publishPage: true
links:
    -
        label: "Paper"
        url: "http://www-sop.inria.fr/reves/Basilic/2021/YASBS21/CASSIE_author_version.pdf"
    -
        label: "Supplemental"
        url: "http://www-sop.inria.fr/reves/Basilic/2021/YASBS21/CASSIE_Supplemental_Material.pdf"
    -
        label: "3D sketches viewer"
        url: "https://ns.inria.fr/d3/CASSIE/sketch-explorer/"
    -
        label: "Data"
        url: "https://gitlab.inria.fr/D3/cassie-data"
    -
        label: "Code"
        url: "https://gitlab.inria.fr/D3/cassie"
    -
        label: "Executable"
        url: "https://ns.inria.fr/d3/CASSIE/CASSIE-build-2021-05-02.zip"
---

## Abstract

We present CASSIE, a conceptual modeling system in VR that leverages freehand mid-air sketching, and a novel 3D optimization framework to create connected curve network armatures, predictively
surfaced using patches with $C^0$
continuity. Our system provides
a judicious balance of interactivity and automation, providing a
homogeneous 3D drawing interface for a mix of freehand curves,
curve networks, and surface patches. Our system encourages and
aids users in drawing consistent networks of curves, easing the
transition from freehand ideation to concept modeling. A comprehensive user study with professional designers as well as amateurs
(N=12), and a diverse gallery of 3D models, show our armature and
patch functionality to offer a user experience and expressivity on
par with freehand ideation, while creating sophisticated concept
models for downstream applications.

## Video preview

{{< youtube ppJrLxi_zfs >}}

## Short summary

3D sketches contain lots of 3D information, yet their lack of structure (a soup of stroke primitives) makes them difficult to re-use in downstream processes, such as the creation of a 3D model.

Humans, especially when not experienced with VR sketching, are inherently not very good at precisely sketching in 3D. This is one of the root to that “lack of structure” problem: it is pretty hard to sketch intersecting strokes in 3D.

{{< figure src="/media/figures/CASSIE/bad-precision-square.gif" caption="Attempt at drawing a square freehand in VR" width="300">}}

So we propose to augment VR sketching with automatic neatening and structuring of strokes. Each stroke that the user creates is minimally reshaped to intersect with nearby strokes.

{{< figure src="/media/figures/CASSIE/input-neatened.gif" caption="" width="500">}}

Structuring the sketch on-the-fly enables us to build a curve network representation of the sketch, which we can use to infer surface patches.

{{< figure src="/media/figures/CASSIE/mouse-surfaces-2.gif" caption="" width="500">}}

This helps with occlusion, making the sketches easier to visually parse. It also enables using sketching as a medium for 3D modelling: the result is a 3D surface!

{{< figure src="/media/figures/CASSIE/turntables-2.gif" caption="Sketches done with our system by 2 of the authors and 1 participant" width="500">}}

So the 3D surface can be used for fabrication, or further refinement via sculpting.
NB: we don’t guarantee 3D-printability properties for the resulting mesh, but simple remeshing in eg Meshlab does the trick.

{{< figure src="/media/figures/CASSIE/applications.png" caption="(a) 3D prints, (b) structural analysis and [truss generation](https://www.dgp.toronto.edu/projects/michell/), (c) fine sculpting in ZBrush, (d) presentation rendering.">}}

Automatic neatening and surfacing features offer a trade-off: loss of user control over their strokes VS a neater, fleshed out result. We investigate in a user study whether this holds up against unconstrained 3D sketching, and find out that users rate our system on-par with freehand sketching on a scale evaluating creativity support (CSI).

We think that understanding 3D sketches and using 3D sketching as a modelling interface are very exciting avenues of research and hope to support future effort by releasing the code for our Unity prototype application, as well as all data from the sketches done during the user study, and those showcased in the paper.

You can explore the sketches in 3D [here](https://ns.inria.fr/d3/CASSIE/sketch-explorer/).


## Supplemental videos

* [Longer video with narration](https://youtu.be/X26Q8oQ7j6M)
* [3 non-edited sketching sessions](https://youtu.be/A3ORhg8OeBE)
* [Gravity Sketch workflow comparison](https://youtu.be/gSlQRHze0dI)

## Acknowledgments

We thank our study participants for their time and effort, and
the anonymous reviewers for their helpful comments. This work
was supported by ERC Starting Grant D3 (ERC-2016-STG 714221),
NSERC Discovery Grant 480538, and by software and research
donations from Adobe.