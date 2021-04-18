# Graft
Graft is a currently under development VSCode extension for describing and visualizing different relationships between items in a base of knowledge. There are many ways to tie information together - hierarchically, such as in an outline, as well as more flat hyperlinked structures such as Wikipedia. Graft is a tool for applying structure to a knowledge base, and doing useful things with that structure.

## Basics
Graft operates entirely on plaintext markdown files (we'll call them leaflets). Important metadata is specified at the head of the file, in a section called frontmatter. It looks like this:
```
---
id:
title:
desc:
extends:
implements:
updated:
created:
---

<body of file>

```
This format is inspired by [Dendron](https://www.dendron.so/).

Graft is centered on the two fields `extends` and `implements`. They are almost identical in meaning to their counterparts in Java. 
* If one leaflet extends another, it is a variation on it - it inherits the attributes of that leaflet, and adds additional information to it. For example, you could have a Mammal leaflet, with Mouse, Cat, and Dog leaflets extending it. You could have Golden Retriever and Pitbull leaflets extending Dog, and so on and so forth. A leaflet can only extend one other leaflet.
* If one leaflet implements another, it is relying on the contents of that leaflet in some regard. A Dog leaflet could implement a Tail leaflet and a Nose leaflet, for example. If the Mammal leaflet implements an Eye or Foot leaflet, the Dog leaflet would inherit that leaflet, and as such would indirectly implement it.

## Usage
Use Graft to construct a system of notes. The note body is for recording information - Graft metadata is for quantifying how concepts actually fit together. By building a system of knowledge, instead of merely recording it, you are gaining a more fundamental understanding of the topic. It also increases the overall power of your knowledge base. You are able to better see how things fit together and get a sense of their importance right away, instead of gradually as you apply your knowledge.

Where Graft really shines is for teaching and review. After you construct and simplify your graph of knowledge, you can more efficiently traverse it. Graft will generate different Manifests based on the knowledge base, each ordering leaflets in a specific way. You can go top-down, bottom-up, order based on frequency, or based on saturation - an order that gives you the "deepest" understanding with the fewest nodes.

## Features
* Graph View (planned) - display a visual, interactive graph of your knowledge base
* Outline View - view and access notes from an outline, matching either the Extends or Implements hierarchy
* Manifests - Generate a recommended order to review or learn notes in based on a couple factors
