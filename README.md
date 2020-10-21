[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rohitma38/sing-alike-interactive/blob/main/demo_colab.ipynb)

# sing-alike-interactive
This demo is a prototype of a system that tells you which popular artist you sound most like, based on a recorded sample of your singing voice. The implementation currently has been built with 4 Indian popular music artists - [Arijit Singh](https://open.spotify.com/artist/4YRxDV8wJFPHPTeXepOstw), [Atif Aslam](https://open.spotify.com/artist/2oSONSC9zQ4UonDKnLqksx), [Lata Mangeshkar](https://open.spotify.com/artist/61JrslREXq98hurYL2hYoc), [Chinmayi](https://open.spotify.com/artist/5UJ2sHO2ELrgW6aXeRLTQQ).

## How the system was built
We obtained some recordings of each artist, separated the vocals using [Spleeter](https://github.com/deezer/spleeter) and obtained embeddings on 10-second chunks using [Resemblyzer](https://github.com/resemble-ai/Resemblyzer). These embeddings are 256-length vectors, that are supposed to "encode" the essential characteristics of the voice. We then used the UMAP supervised projection to learn a reduced 2-dimensional space for these embeddings.

Given a test sample, we first encode it, use the same projection to reduce its dimensionality and classify it using a simple k-nearest neighbors method.

### Acknowledgements
This tool was built as a hack during the first MusicHackDay India in December 2019 organised by [MusicTechCommunity India](https://musictechcommunity.org/).
