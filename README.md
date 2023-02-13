# twin-identifier-analysis

How many local unique identifiers overlap between each biomedical vocabulary in the Bioregistry?

This analysis is inside the [Jupyter notebook](twin-identifier-analysis.ipynb) in this repository. Note that running
this notebook requires quite a bit of setup for [`pyobo`](https://github.com/pyobo/pyobo) and caching of data, so I
haven't carefully added installation/reproduction instructions.

**Results**: There are a bit more than 300 resources in the Bioregistry that can be parsed with PyOBO. 134 of those were
parsable and had more than 10 identifiers. Almost all of them have meaningful overlap with at least one other
resource.

**Take-away message**: Using prefixes is vital to disambiguate between different namespaces. Endpoints like the neXtProt
term endpoint (as discussed in https://github.com/biopragmatics/bioregistry/issues/721) could have collisions between
local unique identifiers from resources like MeSH and NCIT.

Outputs:

- [graph.graphml](graph.graphml) - A generic graph format
- [graph.cytoscape.json](graph.cytoscape.json) - A JSON format compatible with Cytoscape
- [nodes.tsv](nodes.tsv) and [edges.tsv](edges.tsv) - Generic tab-separated values files describing the contents of the
  graph
