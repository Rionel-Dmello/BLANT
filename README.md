#BLANT - Short Documentation
## Analogy with **BLAST**
If you are in the bioinformatics field, you have probably heard of the tool named *BLAST*, the *Basic Local Alignment Search Tool*. BLAST is an algorithm for quickly finding local alignments in genomic (or proteomic) sequences. BLAST works by first creating a comprehensive database of all *k*-letter sequences (called "*k*-mers") that appear in the corpus of sequence to be searched and/or aligned. Such *k*-mers can be used to "seed" a local alignment between two distant regions of sequence. Below we show a hypothetical alignment between two distance regions of sequence, both of which contain the *boldfaced** *k*-mer "**GAGACCGT**":

  ACTAGATCCACCTCTAGGCAGGTAA **GAGACCGT** TGTTCTTCAGAGGTGAAGGAGACGCACAAACGGGCCC
  ACTAGATACACGTCTAGGCAGGTAG **GAGACCGT** AGTTCTTCATAGGTGACGGAGACGCACAAACGGGCCC

By storing every *k*-mer and its location, BLAST can "line up" the regions around two identical *k*-mers, and then check to see if this local alignment "extends" further beyond the *k*-mers. In the case above, even though the sequences contain minor differences, the fact that they contain the depicted *k*-mer seed means we can still find the near-perfect match. BLAST is extremely fast at performing the above operations, which is the reason BLAST has become the near-ubitquitous tool for comparing and aligning sequences that contain billions of letters. BLAST automaticall chooses the appropriate value of *k* to use in a particular search and alignment task. The general name for methods like this is *seed-and-extend* methods.

BLANT (*Basic local Aligment Network Tool*) is intended for form the basis of a tool similar to BLAST, but for networks: given an undirected network *G* as a list of edges, and a value of *k*, it samples *k*-node subgraphs called *k-graphlets*. Since the number of *k*-graphlets in a graph of *n* nodes is exponential in both *k* and *n*, BLANT does not exhaustively enumerate all *k*-graphlets, but instead samples as many as the user specifies. Furthermore, since uniform random sampling of *k*-graphlets is difficult, there are several choices among sampling methods, each with different trade-offs. Finally, BLANT allows for several different methods of output: it can produce *orbit-degree vectors* (ODVs) like *ORCA* (citation), or it can produce an explicit list of *k*-graphlets that can be used as seeds for later extension. At present, BLANT does not provide an "extend" functionality; there are *many* seed-and-extend local alignment algorithms in the literature, and although BLANT currently is by far the fastest method of producing a large number of seeds, we have not yet implemented or tested any extend algorithms; this is an area of future work. Despite the lack of an "extend" feature, BLANT is still capable of useful bioinformatics, as described in our first tool paper in the journal *Bioinformatics* (citation).

## BLANT USAGE
### Command-line arguments
bla bla bla

# BLANT: brief description of source code structure
