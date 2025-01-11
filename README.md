# Brain-Score
This repository shows an example of using the Brain-Score-Vision package, and demonstrates a small experiment of how alignment of ANNs to neuroanatomy (i.e. visual cortex) can enhance brain-likeness.

Specifically, I will try to benchmark my own models with brain-score and, in a simplified way, test the effectiveness of aligning object-detection models with neuroanatomy (visual cortex). I tried to base my code on the [official tutorial](https://github.com/brain-score/candidate_models/blob/master/examples/score-model.ipynb), but it seems to be deprecated as not even the imports work. In the end, not even the guides on the brain-score website helped me, so I had to dive into the implementation of the packages themselves. After lots of trial-and-error, I finally made it work properly.

We are using a simple, non-brain-aligned model with a few layers as baseline. For testing the effectiveness of alignment to neuroanatomy, we will try a simplified version of the CORnet-S model, as proposed in the [original paper](https://papers.nips.cc/paper_files/paper/2019/file/7813d1590d28a7dd372ad54b5d29d033-Paper.pdf). We are given three convolutional layers that represent V1, V2 and V4 areas, and one linear layer for the output, which will represent the IT layer. Since we are benchmarking on V4 neuronal recordings, we will directly map the third convolutional layer without trying out other layers.

The results show that this kind of neuroanatomical alignment pays off to achieve brain-likeness. **With this very simple Feed-Forward Network, we already achieved a score of 0.312 instead of 0.138 for the first model!**

![image](https://github.com/user-attachments/assets/06de0994-b656-4cb8-965a-ebc3fab25c41)
