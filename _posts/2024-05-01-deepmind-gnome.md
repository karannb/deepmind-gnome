---
layout: distill
title: Graph Networks for Materials Exploration
description: A new approach to materials discovery using graph neural networks.
tags: distill formatting
giscus_comments: true
date: 2024-05-24
featured: true

authors:
  - name: Blog Post under double blind review.
    url: "https://example.com"
    affiliations:
      name: GRaM Workshop, ICLR 2024
#   - name: Albert Einstein
#     url: "https://en.wikipedia.org/wiki/Albert_Einstein"
#     affiliations:
#       name: IAS, Princeton

bibliography: distill-template/2018-12-22-distill.bib

# Optionally, you can add a table of contents to your post.
# NOTES:
#   - make sure that TOC names match the actual section names
#     for hyperlinks within the post to work correctly.
#   - we may want to automate TOC generation in the future using
#     jekyll-toc plugin (https://github.com/toshimaru/jekyll-toc).
toc:
  - name: Introduction
    subsections:
        - name: Traditional Methods and Problems
        - name: Materials Project and AI
  - name: Graph Neural Networks (GNNs) & Geometric Deep Learning
  - name: GNoME
    subsections:
        - name: Architecture
        - name: Post-Processing
  - name: Code Blocks
---

## Introduction

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/2024-05-01-deepmind-gnome/unnamed.webp" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The scale difference in materials discovery brought about by GNoME. (Image Credit: DeepMind)
</div>

### Traditional Methods and Problems

Non-Deep-learning based approaches rely on human chemical intuition, domain knowledge, and extensive experimentation to discover new materials. These methods are time-consuming and expensive, and often fail to discover materials with novel properties. This is so because resources as well as human knowledge is limited, and allows for a constrained search space.

ADD MORE CONTENT AND MAYBE DIAGRAMS
Pointers - 
- Cite papers with traiditional methods?
- Put in numbers of experiments or cost for a particular field (e.g. battery materials)?
- Add a diagram of Stable Materials known to humanity over time?

### Materials Project and AI

The Materials Project is a huge database of stable materials and their various properties, it significantly increased materials research by computational methods, but these methods [CITE SOMETHING HERE] still rely heavily on human knowledge for verification.

With the recent advances in other domains using AI, (Machine Perception, Natural Language Processing, etc.), it is a natural question to find if AI can be used to discover new stable materials. The deep-learning based research in most areas has sped up immensely once architectures to capture the inductive bias in the data were developed (e.g. CNNs for images, Transformers for NLP); when these networks are scaled, they demonstrate remarkable out of domain generalization capabilities. A similar emergence occurs with GNoME, GNNs and the field of Materials Science. (Even more so with Geometric Learning which respects underlying physical laws)

## Graph Neural Networks (GNNs) & Geometric Deep Learning

[ADD DIAGRAM]()

GNNs are a unique and relatively new class of neural networks that are built to operate on graph-structured data. They can process an arbitrary sized graph, and can learn both with and without external features (CITE NODE2VEC AND GRAPHSAGE). Internally, a basic GNN will be a stack of permutation-invariant layers, which involve a message passing mechanism between nodes and their neighbors (this can also use edge level features, as well as encode edges). Overall a permutation-equivariant representation is learned for the full graph. 

With this simple structure, we can solve a lot of real world tasks, but, we can augment this further to respect the underlying physical laws of the system. This is where Geometric Deep Learning comes in. It is a field that aims to develop deep learning methods that respect the underlying geometry of the data. This is particularly useful in the case of materials science, where the underlying structure of the material is a graph (atoms are nodes, bonds are edges). This will allow message passing to be more meaningful, and the network to learn more about the system. A general survey of the field is [SURVEY].

## GNoME

GNoME is a radically different and new approach to this problem. It completely removes the need of human intervention in all stages of the pipeline from data pre-processing to final validation. Researchers have also independently developed automated synthesis machines/robots (which also employ AI!), thus allowing the order of magnitude increase in the number of experiments that can be conducted. GNoME also employs Active Learning in a very novel way to boost data availability.

### Architecture

(INSERT DIAGRAM)
GNoME employs two separate architectures for the same task, where each processes a different "view" of the crystal, i.e., either compositional or structural. This is done to increase model exploration and also to give the model more expressive power. These networks have a single function to predict the stability of the crystal, and are trained end-to-end. The final prediction is a weighted average of the two networks.

### Post-Processing

The post-.

## Code Blocks

[CODE?]