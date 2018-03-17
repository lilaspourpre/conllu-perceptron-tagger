## improve results on devset and testset on French CONNLU

F1 | devset | testset | 
--- | --- | --- | 
baseline | 96,42 | 95,71 |
baseline - 'i tag+i-2 tag' | 96,42 | 95,67 |

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
