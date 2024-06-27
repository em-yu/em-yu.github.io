---
title: "3D-Layers: Bringing Layer-Based Color Editing to VR Painting
"
date: 2024-05-05T11:26:00+01:00
journal: "ACM Transactions on Graphics (SIGGRAPH) - 2024"
authors:
    - 
        name: "Emilie Yu"
        url: "https://em-yu.github.io"
    - 
        name: "Fanny Chevalier"
        url: "http://fannychevalier.net/"
    - 
        name: "Karan Singh"
        url: "https://www.dgp.toronto.edu/~karan/"
    -
        name: "Adrien Bousseau"
        url: "https://www-sop.inria.fr/members/Adrien.Bousseau/"
teaser: "pig_small_teaser.jpg"
bigTeaser: "figures/3DLs/teaser_website.png"
bigTeaserCaption: "Our VR painting system allows artists to achieve rich, editable coloring effects using 3D-Layers. Starting with substrate layers (a) that define the geometry and basic colors of the scene, users can stack multiple appearance layers (b) that are composited onto the substrate to produce the final 3D scene (c). Importantly, strokes painted in appearance layers only recolor the substrate strokes they intersect (b, intersections highlighted with a yellow boundary), which avoids the need to position the appearance strokes precisely on the surface of the substrate. In this example, we used appearance strokes to add texture details (white bands on the lighthouse, dark lines on the house and rocks), to paint shadows (lighthouse, rocks), to depict translucency (semi-transparent water painted on the rocks and seabed, subject to a vertical gradient in opacity over the rocks)."
summary: "
    VR artists create beautiful 3D paintings with colored 3D brushstrokes. We investigate how the paradigm of ``painting layers'' could translate to the 3D painting space to achieve non-destructive color editing effects.
"
publishPage: true
links:
    -
        label: "Paper"
        url: "https://www-sop.inria.fr/reves/Basilic/2024/YCSB24/3DLayers-%20Bringing%20Layer-Based%20Color%20Editing%20to%20VR%20Painting.pdf"
    -
        label: "Code"
        url: "https://github.com/graphdeco-inria/3dlayers"
    # -
    #     label: "Supplemental webpage"
    #     url: "https://ns.inria.fr/d3/VideoDoodles/video_doodles_supplemental_webpage"
    -
        label: "Video"
        url: "https://youtu.be/ZTp69Bgt07U"
---

## Abstract

The ability to represent artworks as stacks of layers is fundamental to modern graphics design, as it allows artists to easily separate visual elements, edit them in isolation, and blend them to achieve rich visual effects. Despite their ubiquity in 2D painting software, layers have not yet made their way to VR painting, where users paint strokes directly in 3D space by gesturing a 6-degrees-of-freedom controller. But while the concept of a stack of 2D layers was inspired by real-world layers in cell animation, what should 3D layers be? We propose to define *3D-Layers* as groups of 3D strokes, and we distinguish the ones that represent 3D geometry from the ones that represent color modifications of the geometry. We call the former *substrate layers* and the latter *appearance layers*. Strokes in appearance layers modify the color of the substrate strokes they intersect. Thanks to this distinction, artists can define sequences of color modifications as stacks of appearance layers, and edit each layer independently to finely control the final color of the substrate. We have integrated *3D-Layers* into a VR painting application and we evaluate its flexibility and expressiveness by conducting a usability study with experienced VR artists.


<!-- ## Short summary -->



## Video

{{< youtube ZTp69Bgt07U >}}

<!-- 
## Talk


## Fast Forward

{{< youtube 1eS6KB3MSds >}} -->


## Acknowledgments

We thank our study participants for their time and invaluable insights into their craft. We thank Berend Baas and Gilda Manfredi for help with testing the interface. We thank the anonymous reviewers for their helpful comments. This work was supported by ERC Starting Grant D3 (ERC-2016-STG 714221), Mitacs Globalink Research Award, NSERC (RGPIN-2018-05072) and by software donations from Adobe.