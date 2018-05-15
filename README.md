# JOCI
the JHU Ordinal Common-sense Inference (JOCI) corpus

## Summary
The JOCI corpus is a collection of 39k automatically generated common-sense
inference pairs manually labelled for ordinal inference with the labels
*very likely (5)*, *likely (4)*, *plausible (3)*, *technically possible (2)*,
and *impossible (1)*. JOCI is created to support ordinal common-sense
inference, which is an extension of recognizing textual entailment:
predicting ordinal human responses on the subjective likelihood of an
inference holding in a given context.

See the JOCI [paper](http://www.aclweb.org/anthology/Q17-1027)
for full details. If you use JOCI, please cite:

	@article{ordinal-common-sense-inference,   
		author = {Zhang, Sheng  and Rudinger, Rachel  and Duh, Kevin  and {Van Durme}, Benjamin },  
		title = {Ordinal Common-sense Inference},  
		journal = {Transactions of the Association for Computational Linguistics},  
		volume = {5},  
		year = {2017},  
		keywords = {inference,select},  
		abstract = {Humans have the capacity to draw common-sense inferences from natural language: various things that are likely but not certain to hold based on established discourse, and are rarely stated explicitly. We propose an evaluation of automated common-sense inference based on an extension of recognizing textual entailment: predicting ordinal human responses on the subjective likelihood of an inference holding in a given context. We describe a framework for extracting common-sense knowledge from corpora, which is then used to construct a dataset for this ordinal entailment task. We train a neural sequence-to-sequence model on this dataset, which we use to score and generate possible inferences. Further, we annotate subsets of previously established datasets via our ordinal annotation protocol in order to then analyze the distinctions between these and what we have constructed.},  
		issn = {2307-387X},  
		url = {https://transacl.org/ojs/index.php/tacl/article/view/1082},  
		pages = {379--395},  
	}



## Statistics of JOCI
| Subset Name |  #pair | Context Source |  Hypothesis Source |
|:-----------:|:------:|:--------------:|:------------------:|
|     AGCI    | 22,085 |   SNLI-train   |       AGCI-WK      |
|     AGCI    |  2,456 |    SNLI-dev    |       AGCI-WK      |
|     AGCI    |  2,362 |    SNLI-test   |       AGCI-WK      |
|     AGCI    |  5,002 |   ROCStories   |       AGCI-WK      |
|     AGCI    |  1,211 |   SNLI-train   |       AGCI-NN      |
|     SNLI    |    993 |   SNLI-train   |   SNLI-ENTAILMENT  |
|     SNLI    |    988 |   SNLI-train   |    SNLI-NEUTRAL    |
|     SNLI    |    995 |   SNLI-train   | SNLI-contradiction |
|  ROCStories |  1,000 | ROCStories-1st |   ROCStories-2nd   |
|  ROCStories |  1,000 | ROCStories-1st |   ROCStories-3rd   |
|     COPA    |  1,000 |  COPA-premise  |     COPA-effect    |
|    Total    | 39,092 |        -       |          -         |

## Data Format
We provide the JOCI corpus in the CSV format which has 6 fields:
* **CONTEXT**: the context of the inference pair.
* **HYPOTHESIS**: the hypothesis of the inference pair.
* **LABEL**: the ordinal label for the inference pair.
* **CONTEXT_FROM**: the source of the context, corresponding to the *Context Source* column in the above table.
* **HYPOTHESIS\_FROM**: the source of the hypothesis, corresponding to the *Hypothesis Source* column in the above table.
* **SUBSET**: the subset the inference pair belongs to, corresponding to the *Subset Name* column in the above table.

Here is a bunch of examples:

| CONTEXT                                                                                                                                  | HYPOTHESIS                                | LABEL | CONTEXT_FROM |   HYPOTHESIS_FROM  | SUBSET |
|------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|:-----:|:------------:|:------------------:|:------:|
| John was excited to go to the fair                                                                                                       | The fair opens .                          |   5   |  SNLI-train  |       AGCI-WK      |  AGCI  |
| The politician's argument was considered absurd.                                                                                         | He lost the support of voters.            |   4   | COPA-premise |     COPA-effect    |  COPA  |
| Several bike riders in a parade, wearing American paraphernalia with onlookers nearby.                                                   | People are sitting and watching a parade. |   3   |  SNLI-train  | SNLI-CONTRADICTION |  SNLI  |
| A bare headed man wearing a dark blue cassock, sandals, and dark blue socks mounts the stone steps leading into a weathered old building | A man is in the middle of home building . |   2   |  SNLI-train  |       AGCI-NN      |  AGCI  |
| A brown-haired lady dressed all in blue denim sits in a group of pigeons .                                                               | People are made of the denim .            |   1   |  SNLI-train  |       AGCI-WK      |  AGCI  |

## Related Corpora
* [SNLI](https://nlp.stanford.edu/projects/snli/)
* [ROCStories](http://cs.rochester.edu/nlp/rocstories/)
* [COPA](http://people.ict.usc.edu/~gordon/copa.html)
