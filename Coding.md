Coding Cheat Sheet:
===================

Put all of your fun facts and links to guides here!

- [QuickRef](https://quickref.me/) is a good tool to find cheat sheets for other programming topics.

Required Basics:
----------------
*Software Carpentry* is a great resource for learning how to get started with programming, but its also nowhere near the only one! Still, if you're looking for a place to start, I would start with them:

> <ins>**PRE-REQ:**</ins> You need to have installed all the required software for these tutorials!
> See the [official Software Carpentry installation guide](https://carpentries.github.io/workshop-template/install_instructions/) and our [WSL2 setup guide](https://github.com/VazquezLab/Cheatsheets/blob/main/WSL2SetupGuides.md).

- [Unix shell basics](https://swcarpentry.github.io/shell-novice/)
- [Intro to `git` and version control](https://swcarpentry.github.io/git-novice/)
- GitHub also has a nice [Getting Started](https://docs.github.com/en/get-started/) guide you should look at

> **Note about R vs Python**
> 
> Before you get started with R vs Python, its good to keep in mind that these languages are *tools*.
> 
> Python is a Swiss army knife: you can do almost anything with it, but its not necessarily the best for intensive math or plotting.
> 
> R is the opposite: 10/10 programming and graphing tool, but you might be working 10x as hard using it to edit text and text-like files (e.g. FASTA files).
> 
> Similarly, [`biopython`](https://biopython.org/) is a fantastic resource for processing the most important file types in biology
> (FASTA, multiple sequence alignments, sequencing data...), but it hasn't kept up with the times for newer data types (e.g. VCF, PAF)
> 
> Meanwhile, R has [`Bioconductor`](https://bioconductor.org/) and [`ggplot`](https://ggplot2.tidyverse.org/) which means I will generally
> use R for most analyses, but I wouldn't use it for nitty-gritty file manipulation.
>
> As you learn more, you'll find yourself using one or the other more often depending on what you're doing, but it is important to be fluent in both!

- [Programming with Python](https://swcarpentry.github.io/python-novice-inflammation/)
- [Plotting and programming with Python](https://swcarpentry.github.io/python-novice-gapminder/)
- [Programming with R](https://swcarpentry.github.io/r-novice-inflammation/)
- [R for Reproducible Scientific Analysis](https://swcarpentry.github.io/r-novice-gapminder)

Markdown, YAML, and other "pretty" file formats:
---------
- [GitHub's Markdown syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github)
- [YAML beginner's guide](https://circleci.com/blog/what-is-yaml-a-beginner-s-guide/) and [YAML QuickRef](https://quickref.me/yaml.html)
- [RMarkdown](https://rstudio.github.io/cheatsheets/html/rmarkdown.html)


Terminal & Command Line:
------------------------

- [One of many `zsh` guides](https://opensource.com/article/19/9/getting-started-zsh)
- [Beginner's guide to tmux](https://github.com/tmux/tmux/wiki/Getting-Started)


Phylogenetics:
--------------

- R:
  - [Overview of phylogenetics tools in R](https://cran.r-project.org/web/views/Phylogenetics.html)
  - `ape`: the original phylogenetics in R package.
  - `phytools` & `geiger`: the other most common packages for doing evolutionary analyses in R
  - `ggtree`, `tidytree`, and `treeio`: tidyverse-inspired tools for phylogenetic data wrangling and plotting.
- [Mesquite](https://www.mesquiteproject.org/): an all-in-one phylogenetics toolkit, useful for doing more interactive data exploration and editing.
- [TreeViewer](https://treeviewer.org/): like Mesquite, its a modular all-in-one solution for tree visualization and manipulation - but its much newer. That means that its UI is much nicer, but also it has less features and helpful online tutorials.
- [IQ-TREE](https://iqtree.github.io/): everyone's go-to for making phylogenetic trees!
- [HyPhy](https://github.com/veg/hyphy) and the [DataMonkey Server](https://datamonkey.org/): the go-to software toolkit for selection analysis using protein-coding multiple sequence alignments
  


SQL:
----
- [Software Carpentry: SQL & Databases intro](https://swcarpentry.github.io/sql-novice-survey/)
