---
title: "Piecewise-Smooth Surface Fitting onto Unstructured 3D Sketches"
date: 2022-06-01T14:26:10+01:00
journal: "ACM Transactions on Graphics (SIGGRAPH) - 2022"
authors:
    - 
        name: "Emilie Yu"
        url: "https://em-yu.github.io"
    - 
        name: "Rahul Arora"
        url: "https://rahularora.xyz/"
    - 
        name: "J. Andreas Bærentzen"
        url: "https://people.compute.dtu.dk/janba/"
    -
        name: "Karan Singh"
        url: "https://www.dgp.toronto.edu/~karan/"
    -
        name: "Adrien Bousseau"
        url: "https://www-sop.inria.fr/members/Adrien.Bousseau/"
teaser: "surfacing_3D_sketches.png"
bigTeaser: "figures/surfacing_3D_sketches/Teaser.png"
bigTeaserCaption: "3D sketches created in Virtual Reality (VR) or with sketch-based modeling systems often depict piecewise-smooth surfaces (a), but lack proper inter-stroke connectivity to detect the individual surface patches, as illustrated in the insets where pen strokes do not intersect precisely, and where detail strokes lie on the imaginary surface without being connected to other strokes. State-of-the-art surfacing algorithms only produce smooth surfaces from such sparse and unstructured 3D data (b). Our algorithm segments such an initial smooth surface into regions aligned with the pen strokes to produce a piecewise-smooth surface that better captures the intended shape. ©James Robbins, used with permission."
summary: "
    We propose a method to transform unstructured 3D sketches into piecewise smooth surfaces that preserve sketched geometric features.
"
publishPage: true
links:
    -
        label: "Paper"
        url: "http://www-sop.inria.fr/reves/Basilic/2022/YABSB22/surfacing_sketches.pdf"
    # -
    #     label: "Supplemental"
    #     url: "#"
    -
        label: "Results webpage"
        url: "https://ns.inria.fr/d3/Surface3DSketch/results-page"
    -
        label: "Code"
        url: "https://gitlab.inria.fr/D3/surface-fitting-3d-sketches"
    -
        label: "Dataset"
        url: "https://gitlab.inria.fr/D3/3d-sketches-curated-dataset"
    -
        label: "Presentation"
        url: "https://youtu.be/YqpYrr4n6lU"
---

## Abstract

We propose a method to transform unstructured 3D sketches into piecewise smooth surfaces that preserve sketched geometric features. Immersive 3D drawing and sketch-based 3D modeling applications increasingly produce imperfect and unstructured collections of 3D strokes as design output. These 3D sketches are readily perceived as piecewise smooth surfaces by viewers, but are poorly handled by existing 3D surface techniques tailored to well- connected curve networks or sparse point sets. Our algorithm is aligned with human tendency to imagine the strokes as a small set of simple smooth surfaces joined along stroke boundaries. Starting with an initial proxy surface, we iteratively segment the surface into smooth patches joined sharply along some strokes, and optimize these patches to fit surrounding strokes. Our evaluation is fourfold: we demonstrate the impact of various algorithmic parameters, we evaluate our method on synthetic sketches with known ground truth surfaces, we compare to prior art, and we show compelling results on more than 50 designs from a diverse set of 3D sketch sources.


## Short summary

3D sketches done in VR are beautiful to behold and effectively perceived by viewers, yet are non-trivial to transform into 3D surface models for further design communication and processing. That is because they are sparse and unstructured, the strokes do not form a well-connected curve network with precise intersections (see Fig. 1c). Many on-surface details are also sketched (Fig. 1b), which help perceive the surface but make it challenging to structure the sketch into a curve network a posteriori.

{{< figure src="/media/figures/surfacing_3D_sketches/Sketch-gallery.png" caption="Fig. 1. 3D sketches done in VR (right,©James Robbins, used with permission). " width="600">}}

Based on the observation that the artists explicitly depict sharp features of the surface with strokes (Fig. 1a inset, dashed green lines), we propose a method to transform an initial globally smooth "proxy" surface (Fig. 2b) -- which can be obtained with previous methods or modelled easily by the artists -- into a piecewise-smooth surface where sharp features align with sketched geometric features (Fig. 2d).

{{< figure src="/media/figures/surfacing_3D_sketches/Overview.png" caption="Fig. 2. Overview of our method. " width="">}}

After projecting the sketch onto the proxy, our goal is to segment the proxy into regions, each associated with a smooth surface model, such that the resulting piecewise-smooth surface satisfies the following desiderata.

* **Reproducing stroke geometry.** The surface models should run close to the input strokes, both for strokes that depict sharp surface discontinuities and for strokes that depict details within smooth areas.
* **Aligning patch boundaries with strokes.** The boundary be- tween neighboring regions should lie along strokes that depict sharp surface discontinuities, yet not all strokes in the sketch depict a discontinuity.
* **Keeping the reconstruction simple.** The surface should be composed of a small number of smooth patches, rather than many intricate patches that would overfit to inaccuracy in the input strokes.

We formulate these competing requirements as energy terms in an optimization. We find a local optimum by alternating between optimizing the segmentation while keeping the surface model parameters fixed, and optimizing for the surface model parameters while keeping the segmentation fixed (Fig. 2c).

Here are some results:

{{< figure src="/media/figures/surfacing_3D_sketches/result_matrix_a.png" caption="Fig. 3. Some results. The proxy surface (b) is either obtained with *VIPSS* [Huang et al. 2019] (grey surfaces) or by manual modelling (black surfaces)" width="">}}

Note that our method can fit piecewise-smooth surfaces even onto freehand imprecise sketches (*author2_guitar*) or sketches that present a strong amount of oversketching (*swh_vr_controller*).

Please have a look at our [result webpage](https://ns.inria.fr/d3/Surface3DSketch/results-page) that presents all 50+ results, in the form of interactive 3D viewers.

## Talk

{{< youtube YqpYrr4n6lU >}}


## Fast Forward

{{< youtube 1eS6KB3MSds >}}

## Supplemental video

{{< youtube FAbqQsmQVhc >}}



## Acknowledgments

We thank the artists who kindly shared some of their artworks with us, James Robbins, Jacopo Colò, Arturo Tolentino. We thank the anonymous reviewers for their helpful comments. This work was supported by ERC Starting Grant D3 (ERC-2016-STG 714221), NSERC, Advokat Bent Thorbergs Fond (66.531) and by software and research donations from Adobe.