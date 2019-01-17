# MM-Tag
This is an implementation of MM-Tag which is a MCTS enhanced MDP model. More detail can be seen at https://arxiv.org/abs/1804.10911
The dataset we used is CoNLL2003 (Name Entity Recognition)

cnn-lstm: MM-Tag with char feature <br>
new-value: MM-Tag with new implementation of value network. (highly recommanded to read! It achieved the best result.)<br> 
policy-gradient: the policy-gradient model under the same MDP setting for sequence labeling.

Evaluation metric:
Entity Level F1 score. note that in MM-Tag, label level F1 is our reward.<br> 
The training process between step and reward/loss is shown by:
![Alt text](./new_value/train_fig.png?raw=true "training process")


### DATA

The experiments use the CoNLL-2003 shared task data files contain four columns separated by a single space. 
Each word has been put on a separate line and there is an empty line after each sentence. 
The first item on each line is a word, the second a part-of-speech (POS) tag, the third a syntactic chunk tag and the fourth the named entity tag. 
The chunk tags and the named entity tags have the format I-TYPE which means that the word is inside a phrase of type TYPE. Only if two phrases of the same type immediately follow each other, the first word of the second phrase will have tag B-TYPE to show that it starts a new phrase. 
A word with tag O is not part of a phrase. Here is an example:

```
   U.N.         NNP  I-NP  I-ORG 
   official     NN   I-NP  O 
   Ekeus        NNP  I-NP  I-PER 
   heads        VBZ  I-VP  O 
   for          IN   I-PP  O 
   Baghdad      NNP  I-NP  I-LOC 
   .            .    O     O 
```

In the following links there are [more about CoNLL-2003](https://www.clips.uantwerpen.be/conll2003/ner/)

