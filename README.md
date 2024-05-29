# hidden-citation

This is the public repository for Xiangyi Meng, Onur Varol, and Albert-László Barabási, "Hidden Citations Obscure True Impact in Science". The repo consists of two Mathematica notebooks (ArxivNetHiddenCitationParse.nb and ArxivNetHiddenCitationLDA.nb) and all intermediate results (subGPhy10000/).

__ArxivNetHiddenCitationParse.nb__: Parse the citation context using Mathematica's built-in functions.

- Input: Citation contexts of the top 10,000 cited papers in physics (extracted from arXiv), which we provide in subGPhy10000/subGPhy10000Context.mx. For details of the extraction of the citation contexts please refer to the unarXive dataset (https://doi.org/10.5281/zenodo.4313164).

- Output: (1) Parsed citation contexts (subGPhy10000/subGPhy10000Corpus_210204.mx); (2) A dictionary of 100,000 n-grams (subGPhy10000/subGPhy10000tfidf100000_210312.mx).

- Execution: Evaluate the whole notebook.




__ArxivNetHiddenCitationLDA.nb__: A synchronous parallel implementation of the collapsed Gibbs sampling method for the latent Dirichlet allocation algorithm (LDA).

- Input: (1) Parsed citation contexts (subGPhy10000/subGPhy10000Corpus_210204.mx); (2) Dictionary of n-grams (subGPhy10000/subGPhy10000tfidf100000_210312.mx).

- Output: (1) Conditional probabilities between n-grams, documents, and their topics (subGPhy10000/subGPhy10000tfidf100000LDA2000_P.mx); (2) Specific conditional entropies (uncertainties) of each conditional probability distribution
(subGPhy10000/subGPhy10000Entropies_210312.mx).

- Execution: Evaluate the whole notebook (the core cell "Gibbs Sampling" may be re-evaluated multiple times for updating the results).
