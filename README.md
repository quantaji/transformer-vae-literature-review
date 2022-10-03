# Literature Review on Autoregressive VAEs

The paper that begin with "(Cited)" means this paper is cited by the previous work *Learning to Drop Out: An Adversarial Approach to Training Sequence VAEs*, so some of us might have already read them.

## Papers related to combination of Transformer/Seq2Seq and VAEs
1. [A Transformer-Based Variational Autoencoder for Sentence Generation](https://ieeexplore.ieee.org/document/8852155)
   1. one of the frist attempt to combine Transformer with VAEs
   2. in a way that is different from Optimus
2. [Implicit Deep Latent Variable Models for Text Generation](http://arxiv.org/abs/1908.11527) (recommand)
   1. iVAE, turn explicit VAE (gaussian) into implicit and use sampling.
   2. also modified original KL loss with mutual information.
   3. more details in his PhD thesis [Towards Effective and Controllable Neural Text Generation](https://www.proquest.com/openview/f6eca04f702304681b11aee1ca8ee531/1?pq-origsite=gscholar&cbl=51922&diss=y)
3. [Variational Transformers for Diverse Response Generation](http://arxiv.org/abs/2003.12738) (recommand)
   1. propose two kind of combination of Transformer and VAEs, GVT and SVT
   2. GVT encodes input sentence as first token vector and fed it to decoder, but still have posterior collapse
   3. SVT is interesting, the latent code is also generated in an autoregressive fasion for prior network, and non-autoregressive for posteior network.
4. [Addressing Posterior Collapse with Mutual Information for Improved Variational Neural Machine Translation](https://aclanthology.org/2020.acl-main.753) (Recommand!)
   1. design a new objective, without weakening the decoder.
5. [Optimus: Organizing Sentences via Pre-trained Modeling of a Latent Space](http://arxiv.org/abs/2004.04092) (need to read)
   1. one of the first attempt to combine BERT + GPT-2 into a VAE model.
6. [FlowPrior: Learning Expressive Priors for Latent Variable Sentence Models](https://aclanthology.org/2021.naacl-main.259)
   1. data-driven expressive prior
7. [Less is More: Pretrain a Strong Siamese Encoder for Dense Text Retrieval Using a Weak Decoder](https://aclanthology.org/2021.emnlp-main.220)
   1. some analysis on OPTIMUS in the area of Dense Reteival, claiming OPTIMUS is not so good as original BERT
8. [Finetuning Pretrained Transformers into Variational Autoencoders](https://aclanthology.org/2021.insights-1.5)
   1. Very similar to OPTIMUS, only instead of self-attention in GPT-2, they inject cross-attention in Transformer
9. [Transformer-based Conditional Variational Autoencoder for Controllable Story Generation](http://arxiv.org/abs/2101.00828)
   1. this work considers Conditional VAE instead of VAE, the goal is a little different, so a little off-topic.
   2. they design a pseudo attention, new way to inject enc-dec dependency.
10. [Controlled Text Generation Using Dictionary Prior in Variational Autoencoders](https://aclanthology.org/2022.findings-acl.10) (recommand)
    1. also data driven prior, improving optimus. 

## Empirical methods to prevent posterior collapse
1. (Cited, Everything's begining) [Generating Sentences from a Continuous Space](http://arxiv.org/abs/1511.06349) 
2. (Cited) [Semi-Amortized Variational Autoencoders](https://proceedings.mlr.press/v80/kim18e.html) 
3. (Cited) [Preventing Posterior Collapse with delta-VAEs](http://arxiv.org/abs/1901.03416)
4. (Cited) [Lagging Inference Networks and Posterior Collapse in Variational Autoencoders](http://arxiv.org/abs/1901.05534)
5. [Preventing posterior collapse in variational autoencoders for text generation via decoder regularization](http://arxiv.org/abs/2110.14945)
   1. dropout as augmentation, like SimCSE. to make the hidden space robust.

## Theoretical analysis on general posterior collapse
1. (Cited) [Variational Lossy Autoencoder](http://arxiv.org/abs/1611.02731) 
   1.     Analyze posterior collapse, from the view of information theory and coding.
   2. replace the original gaussian prior with an autoregressive flow, and claim to have better result.
2. (Cited) [Don' t Blame the ELBO! A Linear VAE Perspective on Posterior Collapse](https://proceedings.neurips.cc/paper/2019/hash/7e3315fe390974fcf25e44a9445bd821-Abstract.html) 
3. [The Usual Suspects? Reassessing Blame for VAE Posterior Collapse](https://proceedings.mlr.press/v119/dai20c.html)
   1. this paper gives a good taxonomy of various kinds of posterior collapse.
   2. not on posterior collapse of autoregressive model

## Analysis on posterior collapse particular w.r.t. autoregressive models
1. [Variational Attention for Sequence-to-Sequence Models](http://arxiv.org/abs/1712.08207)
   1. Bypass phenomenon: whenever there is a deterministic information pathway, the varietional part would loss function. 




## Not very Related, but might be insightful
1. [INSET: Sentence Infilling with INter-SEntential Transformer](http://arxiv.org/abs/1911.03892)
   1. not about VAE, but contains many training tricks, might be useful.
2. [Improving Text Generation with Student-Forcing Optimal Transport](https://aclanthology.org/2020.emnlp-main.735)
   1. a little off-topic, about the loss design of autoregressive model, might be useful in training.
3. [Non-Autoregressive Neural Dialogue Generation](http://arxiv.org/abs/2002.04250)
   1. maybe transformer and VAEs can be used in non-autoregressive way. 
4. [Variational Transformer Networks for Layout Generation](http://arxiv.org/abs/2104.02416)
   1. not on text, but on Layout
   2. both auto-regressive (GPT) or non-autoregressive (BERT) fassion are studied.
   3. use a learned prior distribution.
5. [Diffusion-LM Improves Controllable Text Generation](http://arxiv.org/abs/2205.14217)
   1. diffusion model on text! they also do text generation non-autoregressively.

