Welcome! This is a brief tutorial on using [ggtree](https://rdrr.io/github/GuangchuangYu/ggtree/f/README.md) in R to visualize phylogenetic trees. [Here](https://guangchuangyu.github.io/ggtree-book/short-introduction-to-r.html) is a decent overview of ggtree and the various things it is capable of. For this tutorial, I used the phylogenetic trees and information in [Haigh et al. 2022](https://doi.org/10.1002/ajb2.16117), [Lee et al. 2022](https://doi.org/10.1111/jse.12498), [Lee et al. 2021](https://doi.org/10.11110/kjpt.2021.51.1.1), and [Tippery et al. 2021](https://doi.org/10.3390/plants10122639) to create a [nexus file](https://github.com/wjdavis90/Tutorials/blob/main/R/Phylogenetic_trees/skunk_cabbage.nexus). This tutorial also uses this [cvs file](https://github.com/wjdavis90/Tutorials/blob/main/R/Phylogenetic_trees/pretty_names.csv).

First, it is best to install the ggtree package using `devtools::install_github("GuangchuangYu/ggtree")` rather than `install.packages()` as the version on R's CRAN will not work in latter versions of R.

To get started, we need to load some libraries.

```
library(tidyverse)
library(ggtree)
library(ape)
```

Next, we will read in the `.cvs` file. We will use this file to clean up the tip labels. It can also be used to map various data onto the tree.

```
tip_labels <- read.csv("pretty_names.csv", header=TRUE)
```

Next we will read in the tree. We will use `read.tree()` from the ape package.

```
skunk_tree <- read.tree("skunk_cabbage.nexus", text= NULL, tree.names= NULL, skip=0, keep.multi= FALSE)
```

Now let's begin viewing our tree! We will start with something simple.

```
ggtree(skunk_tree, branch.length="none") %<+% tip_labels +
geom_tiplab(aes(label= label_pretty)) +
xlim(NA, 10)
```

`ggtree(skunk_tree)` works similar to ggplot2. `branch.length="none"` let's R know that there are no branch lengths with this dataset. `%<+% tip_labels` appends the dataframe containing the new tip labels and the data we want associated with them to the tree. With `geom_tiplab(aes(label= label_pretty))`, we direct ggtree to the appropriate column within `tip_labels` for the new tip labels. Finally, the ggtree will likely cut off the new tip labels, so we must use `xlim()` to adjust the size of the tree until the labels are not cut off. Let's see the resulting tree.

![first tree image](https://github.com/wjdavis90/Tutorials/blob/main/R/Phylogenetic_trees/images/skunk_cabbage_phylogeny1.tiff)

Now, let's color code the clades according to continent.

```
ggtree(skunk_tree, branch.length="none") %<+% tip_labels +
geom_tiplab(aes(label= label_pretty, color= distribution, fill= distribution)) +
scale_color_manual(name=NULL, values=c("#542788",
							"#8c510a",
							"#1a1a1a",
							"#2166ac")) +
geom_nodelab(aes(label=ages), geom="text", nudge_x=-0.58, nudge_y=0.25) +
theme(legend.position="bottom") +
xlim(NA, 10)
```

[Insert picture]

Now, for the final tree, let's add some node ages. To begin, we need to know how R is numbering the nodes. To do this, we add `geom_text(aes(label=node))`. One might have to play with `hjust` for easy viewing. 

```
ggtree(skunk_tree, branch.length="none") %<+% tip_labels +
geom_tiplab(aes(label= label_pretty, color= distribution, fill= distribution)) +
scale_color_manual(name=NULL, values=c("#542788",
							"#8c510a",
							"#1a1a1a",
							"#2166ac")) +
geom_nodelab(aes(label=ages), geom="text", nudge_x=-0.58, nudge_y=0.25) +
theme(legend.position="bottom") +
xlim(NA, 10)+
geom_text(aes(label=node))
```

[Insert image]

The nodes we are interesting in are 20, 22, and 24. Using dates pulled from the papers cited above, we will make a dataframe within R.

```
node_ages <- data.frame(node=c("20", "22", "24"),
				ages=c("18 mya", "8.78 mya", "1.9 mya"))
```

Now we will append this to the tree and use `geom_nodelab()` to label the nodes.

```
ggtree(skunk_tree, branch.length="none") %<+% tip_labels %<+% node_ages +
geom_tiplab(aes(label= label_pretty, color= distribution, fill= distribution)) +
scale_color_manual(name=NULL, values=c("#542788",
							"#8c510a",
							"#1a1a1a",
							"#2166ac")) +
geom_nodelab(aes(label=ages), geom="text", nudge_x=-0.58, nudge_y=0.25) +
theme(legend.position="bottom") +
xlim(NA, 10)
```

[Insert image]

