# Staggered-Spaces
When storing large related data, chances are there will be a great deal of overlap in the information as a whole. Is it possible to instead of redundantly storing these overlaps, reference stored clusters of overlap when reading in new data? 

# GenericKB Dataset

The initial goal will be to create a referential based way to represent the generickb dataset. We plan to collapse are duplicates until only unique instances of particular words remain, then reference words from the dictionary to minimize the space required to store the data. Fields in GenericsKB-Best.tsv are as follows:

- SOURCE: denotes the source of the generic
- TERM: denotes the category that is the topic of the generic.
- GENERIC SENTENCE: is the sentence itself.
- SCORE: Is the BERT-trained score, measuring the degree to which the generic represents a "useful, general truth" about the world (as judged by crowdworkers). Score ranges from 0 (worst) to 1 (best). Sentences with scores below 0.23 (corresponding to an "unsure" vote by crowdworkers) are in GenericsKB, but are not part of GenericsKB-Best due to their unreliability.
- QUANTIFIER_FREQUENCY:For generics with explicit quantifiers (all, most, etc.) the quantifier is listed - Frequency contains values such as 'usually', 'often', 'frequently'
- QUANTIFIER_NUMBER: For generics with explicit quantifiers (all, most, etc.) with values such as 'all'|'any'|'most'|'much'|'some' etc...