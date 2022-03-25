Here we are going to walk through building an alignment using this [sequence data](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/data/Albugo_cox2.fasta) that were obtained from GanBank. I tytpically use [mafft](https://mafft.cbrc.jp/alignment/server/), either the online version or the commandline version, to build aligments. For this tutorial, we are going to use the [online version of mafft](https://mafft.cbrc.jp/alignment/server/) because it is user friendly and fast. Also, it does not require installing any new software! I also use [AliView](https://ormbunkar.se/aliview/) because it is lightweight and easy to use. However, there are many other good options available for either building or viewing alignments and some may be better suited to your needs.

### Step 1

Open Albugo_cox2.fasta in a sutiable text editor (e.g., [Notepadd++](https://notepad-plus-plus.org/) or [BBEdit](https://www.barebones.com/products/bbedit/). Copy the sequences, go to [mafft's website](https://mafft.cbrc.jp/alignment/server/), and paste them into box as shown in the screenshot below.
![mafft screenshot 1](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/screenshots/mafft-1.png)

### Step 2

![mafft screenshot 2](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/screenshots/mafft-2b.png)
Scroll down the page and make sure the options highlighted by black arrows in the screenshot above are checked.

First black arrow: We want to be sure that all character states are read not just the standard A,T, G, C.

Second black arrow: This will automatically become selected when we select "Allow unusual symbols". However, I prefer to have both nucleotides and amino acids be in uppercase as it is easier to read.

Third black arrow: This one is important, and it is important that the first sequence in our dataset is one we trust. Sometimes people upload seuqences into GenBank in the wrong direction. This can really screw up the alignment! Fortunately, mafft has a way of catching and correcting for this, which is one reason we are using it.

Fourth black arrow: In the output, we want the sequences to be ordered according to how they were aligned. mafft builds alignments progressively. That is, it starts by finding a pair of sequences that are similar to one another and builds the alignment by adding the next most similar sequence, etc, etc. This means that regardless of how they are in the input, the sequences should be grouped by taxa in the alignment. If they are not, then we know something strange is going on. Either there was a msitake in the alignment (common enough) or the taxa are not related the way we think they are (also common).

### Step 3

![mafft screenshot 3](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/screenshots/mafft-3b.png)
Scroll down the page some more until you come to the section shown in the screenshot above. One of the other reasons we are using mafft is because it has an option (shown with the black arrow) to automatically determine the best method of aligning the sequences! Thus, we don't hav eot do this *a priori*. This should be selected by default.

Just above the "submit" button, there should be a field where we can put in an email address. If we do so, it will send us an email when our alignment is done with a link to the alignment. For small datasets such as ours, I generally don't do this. For larger datasets, you will want to as it may take an hour or more to align.

Now we are ready to submit (red arrow above), and we should be taken to a screen such as the one below.
![mafft screenshot 4](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/screenshots/mafft-4.png)
So, we wait until it is done. 

### Step 4

![mafft screenshot 5](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/screenshots/mafft-5.png)
When mafft is done, we will be taken to a screen such as the one shown above. Be sure to scroll down and take a look at the alignment. Part way down, we see that there is only one sequence that had to be reverse complemented (indicated by the black arrow in the screenshot below), and it is marked with "\_R\_".
![mafft screenshot 6](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/screenshots/mafft-6b.png)

Scroll back to the top and right click (for Windows) on "Fasta Format". From the menu select "Save link as..." (again, for Windows). Now enter a name and besure to save it as a fasta. When I did this, I saved it as the file [Albugo_cox2_mafft_alignment_20220324-2.fasta](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/data/Albugo_cox2_mafft_alignment_20220324-2.fasta).
![mafft screenshot 5b](https://github.com/wjdavis90/Tutorials/blob/main/Phylogenetics/screenshots/mafft-5b.png)

### Step 5
