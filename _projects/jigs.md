---
title: "Jigs: Visualized"
order: 2012-08
thumbnail: jigs/jigs_thumb@2x.png
client: Personal
repo: https://github.com/darthmall/Irish-Tune-Visualization
abstract: >-
  A network visualization of relationships between traditional Irish jigs based on melodic similarity.
color: DF4A3F
---

![A network of jigs connected by similarity]({% link assets/img/jigs/network.png %})

## Noise in the Key of D

There's a joke about traditional Irish music that it's all just noise in the key of D, and if you've ever been in a pub during an Irish session you probably understand why: it all sounds pretty much the same. Even those of us that have been playing for a while will confuse which tune is which, and sometimes switch from one tune to another halfway through by accident.

This data visualization attempts to elucidate how much similarity exists in a corpus of Irish jigs taken from [The Session][thesession], an online database of Irish tunes.

## Jig Network

Each tune is represented as a node in a graph. Edges between tunes exist when the melodies of both tunes are similar enough. The more similar two tunes are, the stronger the edge's weight. Using this data structure and a force-directed layout, we can render the tunes in two dimensions such that similar tunes are near each other. Each node is sized according to the weighted degree of that node: the larger the node, the more tunes it's related to. Hovering over a node in the graph highlights that node and all of the nodes connected to it.

A few tunes stand out in this configuration. "Jackson's Fancy", for example, is connected to quite a few other tunes; some are quite close, while others are farther out. Perhaps "Jackson's Fancy" is an archetypal jig, or perhaps it's a newer, more derivative tune composed by stitching together phrases from other tunes.

I used [Gephi][gephi] to create a GraphML file for the network layout which I then rendered with [Processing][processing] to make the interactive version of the network.

## Measuring Similarity

To determine how similar a pair of jigs is, I calculate the [Levenshtein distance][levenshtein] between each pair of jigs using the [ABC notation][abc] for each jig. I normalize the distance by dividing it by the length of the longer of the two tunes. I then set a threshold to exclude edges in the graph that represent a low similarity.

These calculations were all performed with the help of a [Python][python] library for musicology: [music21][music21].

## Visualizing Melody

Originally I had wanted to show not only that the tunes in this corpus were very similar, but *how* they were similar; I wanted to highlight repeated phrases. To that end, some of my early iterations of these visualizations involved trying to represent the melodies of individual tunes to highlight where common phrases occur. Part of what I hoped to achieve here was to do for multiple tunes what Martin Wattenberg's [Shape of Song][shapeofsong] did for individual songs.

<figure>
  <img src="{% link assets/img/jigs/gan_ainm-pianoroll.png %}" />
  <img src="{% link assets/img/jigs/babes_in_the_woods-barcode.png %}" />
  <img src="{% link assets/img/jigs/the_corkin_cross-line.png %}" />
  <figcaption>
    Various representations of overlapping melodies.
  </figcaption>
</figure>

After exploring several visual forms with this goal in mind, I decided that it would be more effective to show the entire corpus at once, rather than trying to focus on individual tunes, thus, the network.

[thesession]: https://thesession.org
[abc]: http://abcnotation.com
[levenshtein]: https://en.wikipedia.org/wiki/Levenshtein_distance
[shapeofsong]: http://www.bewitched.com/song.html
[gephi]: https://gephi.org
[music21]: http://web.mit.edu/music21/
[python]: http://python.org
[processing]: http://processing.org
