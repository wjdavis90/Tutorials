# Introduction

Welcome! I am writing this to a be guide to those who wish to [foray](https://www.merriam-webster.com/dictionary/foray) into molecular phylogenetics, which is itself a subset of systematics. My goal is to provide both a broad base in the theory behind molecular phylogenetics and a general guide into the workflow. In this document, I will breifly describe the layout of this folder, provide some background information on the orgnaisms and the locus I use as examples, and then go into some of the theory behind things. However, one doesn't always have to understand the how and why behind things in order to apply them. Thus, one can always jump to the how to documents, which I will provide links to below.

All of the data/input files I used are included in the [data](https://github.com/wjdavis90/Tutorials/tree/main/Phylogenetics/data) subfolder, and the results/output files are located in the [results](https://github.com/wjdavis90/Tutorials/tree/main/Phylogenetics/results). There, is some overlap between input and output, for example, the output of mafft is the input of raxml. In general, everything that comes before tree inference is in the data subfolder and everything post tree inference is in the results folder. This is because the phylogenetic tree is the goal.

The general workflow for molecular phylogenetics is:
1. Obtain sequence data for the target taxa and/or loci. This is generally study specific and may involve extracting an sequencing DNA and/or mining data repositories. Thus, it is hard to generalize, and I do not (currently) have a how to for this step.
2. [Generating an alignment(s)](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/alignments.md)
3. [Determining the best partition scheme and model of evolution](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/partitionfinder.md)
4. [Inferring a phylogenetic tree](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/tree_inference.md)
5. [Visualizing the phylogenetic tree](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/tree_visulization.md)


# Getting to know the organisms

[![Albugo on Cardamine](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/images/Albugo.jpeg)](https://www.inaturalist.org/observations/75608199)

The organisms I choose to use for this example are white rusts, specifically the genus *Albugo* and its allies. The image above shows a leaf of a [*Cardamine* sp.](https://en.wikipedia.org/wiki/Cardamine) heavily infected with a white rust (the pustules) in the genus *Albugo* (specifically a member of the [*Albugo candida*](https://www.cabi.org/isc/datasheet/4051) [species complex](https://en.wikipedia.org/wiki/Species_complex)). 


*Albugo*, *Pustula*, and *Wilsoniana*

# Theory of Molecular Phylogenetics

## Selection of taxa and loci

## Generating alignments

## Models of evolution & Model selection

## Tree inference

## How to read phylogenetic trees
