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

The white rusts were initially described as fungal taxa in the order Pucciniales; however, it was later realized that they are not Fungi but rather are members of [Oomycota](https://ucmp.berkeley.edu/chromista/oomycota.html). Oomycetes are morphologically and ecologically similar to [Fungi](https://en.wikipedia.org/wiki/Fungus) but differ in key ways, including, but not limited to, cell wall components and lysine synthesis [^1]. Later it was realized that the white rusts were oomycetes. Still later,Thines and Spring (2005)[^2] separated out some taxa and placed them in the new genera *Pustula* and *Wilsoniana* based on a combination of morphology, host ranges, and molecular phylogenetics. Since then there has been a great deal of work done to revise the genera and species using morphology and molecular phylogenetics.[^3] We are going to use the data from some of these studies in this example.






*Albugo*, *Pustula*, and *Wilsoniana*

# Theory of Molecular Phylogenetics

## Selection of taxa and loci

## Generating alignments

## Models of evolution & Model selection

## Tree inference

## How to read phylogenetic trees


[^1]: My Ph. D. advisor Martha Powell (and others, including myself) make the distinction between fungi and Fungi. "fungi" (with a lowercase f) is a morphological and ecological grouping that includes organisms that grow into their food, secrete enzymes to break down that food, and absorb the nutrients released during the breakdown. Additionally, fungi produce spore bearing structures during reproduction. Thus, fungi includes Holomycota (Fungi), oomycetes, and slime molds; it is a [polyphyletic group](https://www.mun.ca/biology/scarr/Taxon_types.htm). "Fungi" (with an uppercase F), on the other hand, only refers to the [monophyletic clade](https://www.mun.ca/biology/scarr/Taxon_types.htm) containing the following characters: chitin cell walls, AAA lysine synthesis, and a posterior, whiplash flagellum. Fungi includes organisms like the mushrooms on pizza and the yeast in bread. (You may be thinking at this point "But Fungi don't have flagella." Au contraire mon amie, [they do](https://youtu.be/MbeU5PKbUrs). 

[^2]: Thines M, Spring O (2005) A revision of Albugo (Chromista, Peronosporomycetes). Mycotaxon 92:443–458 [Cyberliber link](http://www.cybertruffle.org.uk/cyberliber/59575/0092/0443.htm)

[^3]: See, for example, ...lisdt of authors year with doi links
