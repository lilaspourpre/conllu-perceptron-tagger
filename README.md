## improve results on devset and testset on French CONNLU

F1 measure

method | devset | testset | 
--- | --- | --- | 
baseline | 96,42 | 95,71 |
baseline - 'i tag+i-2 tag' | 96,42 | 95,67 |
baseline + 'i len' | 96,46 | 95,77 |
baseline + 'i bigrams' | 96,53 | 95,88 |
baseline + 'i bigrams' + 'word len' | 96,53 | 95,84 |
baseline + 'i trigrams' | 96,66 | 96,01 |
**baseline + 'i trigrams' + 'word len'** | **96,68** | **96,11** |

The following methods reduce F1 measure:
* baseline + 'i-1 len + i len + i+1 len'
* baseline + 'i-1 prefix'
* baseline + 'i+2 suffix'
* baseline + 'i-2 suffix'

# conllu-perceptron-tagger

A (very) simple perceptron tagger for CoNLL-U files, intended for use as a teaching
aid.

This is wholely based on the following code:

* https://explosion.ai/blog/part-of-speech-pos-tagger-in-python
* https://github.com/sloria/textblob-aptagger

I've basically taken the code and wrapped it for parsing CoNLL-U format files. 

# Usage

Like UDpipe:

Train:

```
cat kk-ud-train.conllu | python3 tagger.py -t model.dat
```

Predict:

```
cat kk-ud-test.conllu | python3 tagger.py model.dat > output
```
ә
