# TrojAIPapers

## tianjian10 -- Detection TrojAI Top3; MICO ALl Rounds No.1
* [What is MICO Competition](https://microsoft.github.io/MICO/)
    - [CodaLab Page](https://codalab.lisn.upsaclay.fr/competitions/8551#learn_the_details-overview)

* Inspired by [Membership Inference Attacks From First Principles](https://arxiv.org/abs/2112.03570)
    - [Tianjian's Corresponding Solution](https://github.com/microsoft/MICO/commit/e7ddf3e0329b7315901fb764dca7e3c94e8c0cb5)
    - I am still trying to understand those.

```
 1. Get the outputs of all samples with each model in the training set, calculate the loss and confidence and save them to advoid duplicate computation.
 2. For each sample in the challenge set, collect the $scores_{in}$ and $scores_{out}$, and then calibrate the score in different ways.
 3. (Unnecessary for some tracks)Merge the results from different scenarios.

 As for shadow models, I only used the given 100 models in training set of each track and did not train any extra models. Take CIFAR-10 as an example, the ratio of training and test set is 5:1. That means for any one sample, about 5/6 of 100 models in the training set are IN models which were trained with that sample, and about 1/5 are OUT models.

 As for the selection of calibration equations, I tried in different ways and found the best ones according to the results on validation set for different tracks and different scenarios at present.
```


* Reproduce the method mentioned in above page and change it to fit the competition 
    - [One of Second Place solution](https://github.com/DevPranjal/mico-first-principles)

* [A 2nd Place solution with blog](https://www.anshumansuri.me/post/mico/)
    - [Github](https://github.com/iamgroot42/MICO)
    - Also being inspired by the above paper.
    
* [A solution with jupyter NoteBook](https://github.com/wfleshman/MICO_SST)

* [IEEE SaTML Workshop Recordings](https://satml.org/videos/)
IEEE Conference on Secure and Trustworthy Machine Learning






## TrojanZoo
* Functional tool box on general purpose

* [Official Doc](https://ain-soph.github.io/trojanzoo/tutorials/basic.html)
* [Examples](https://github.com/ain-soph/trojanzoo/tree/main/examples)

* [finePruning](https://github.com/ain-soph/trojanzoo/blob/main/trojanvision/defenses/backdoor/attack_agnostic/fine_pruning.py)


