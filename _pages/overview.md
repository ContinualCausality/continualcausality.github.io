---
permalink: /
title: "Continual Causality Bridge at AAAI 2024"
layout: splash
classes: wide
---

<style type="text/css">
    .image-center {
      display: block;
      margin-left: auto;
      margin-right: auto;
      float: right;
    }
</style>


# Continual Causality

## 2nd Bridge Program at AAAI 2024: 20+21st February 
![image-center](/assets/images/AAAI-24-banner.png){: .align-center style="width:1900px;"} 

**Continual Causality is back for round 2 - proudly sponsored by [hessian.AI](https://hessian.ai), who financially supports our invited speakers!**

![image-center](assets/images/hessian-ai-logo.png){: .align-center style="width:1900px;"} 

#### Bridge Overview
We aim to bring together the fields of *continual learning* and *causality* in a [AAAI-24 bridge program](https://aaai.org/aaai-conference/aaai-24-bridge-program/) called *Continual Causality*. Both fields research complementary aspects of human cognition and are fundamental components of artificial intelligence if it is to reason and generalize in complex environments. Despite some recent interest in bringing the two fields together, including our AAAI-23 bridge program of the same title, it is currently unclear how causal models may describe continuous streams of data and, vice versa, for continual learning to exploit learned causal structure. 

With this bridge program, we aim to continue our first steps towards a unified treatment of these fields and to provide the space for learning, discussions, and to connect and build a diverse community. The activities range from traditional tutorials and real-world
application sessions on the educational side, invited vision
talks and contributed ones based on submitted papers, to a
panel and breakout discussions. All materials will be publicly
disseminated as a foundation for the community, and the respectively discussed ideas, challenges and prospects will be
aggregated to foster continued exchanges beyond AAAI-24

* More in-depth information is provided in below paragraphs and the [bridge format section](http://www.continualcausality.org/format/). 
* The [call for participation](http://www.continualcausality.org/cfp/) outlines how to contribute to the vision and actively join the bridge efforts (submission deadline for 2024 has passed).
* Find information on the invited speakers and detailed schedule in the 2024 [program tab](https://www.continualcausality.org/program/)
* Join our community on [Slack](https://join.slack.com/t/continualcausality/shared_invite/zt-1fwahodl3-7Z8xe_lzxj33qEbTs558kg)
* Email info[at]continualcausality[dot]org for questions  


#### Bridge Perspectives and Areas of Focus

For a machine learning agent to successfully learn in natural settings it has to accommodate often non-linear emergent dynamics from a sea of apparent stochasticity. The last decade has seen spectacular progress in these settings, surpassing human performance across a host of complex tasks. However, it is not only essential to these problems to identify the dependence between variables in observational data and their dynamics, but it is also essential to understand their underlying causation and how their dependencies arise.

Causality theory (Pearl 2009, Peters 2017} provides language, algorithms, and tools to discover and infer cause-and-effect relationships from any collection of observational/experimental data based on a partial understanding of a complex system. The field provides a powerful framework for learning a (partial) representation of the underlying causal model, evaluating the effect of unrealized interventions, reasoning about the effects of stochastic policies, generalizing causal knowledge to a target population, recovering from selection bias, and deriving counterfactual explanations. 
Moreover, there is increasing interest in using the structure and invariances defined by causal models in problems with continuous data distribution shifts. 

In machine learning, many of these problems appear under the rubric of continual learning. Continual learning systems (Chen 2018, Hadsell 2020) learn over time from a continuous stream of data, enable knowledge transfer and alleviate potentially malicious interference when distributional shifts are experienced. At the crux, they achieve the latter without revisiting previously encountered training samples (unless they are in memory), much in contrast to traditional machine learning settings where all training samples are available from the start and can be revisited. 

Both fields, causality and continual learning, thus exhibit complementary strengths. On the one hand causal models formally describe structural similarities between domains that can aid generalization of continual learning systems. On the other hand continual learning systems efficiently navigate complex data collection systems and model streams of data that have not yet been studied from a causal perspective. 


#### Bridge Goals: Challenges and Perspectives

Despite causality having taken huge strides in recent years, causal learning tools are prone to catastrophic interference of past-learned and possibly imperfect representations when new data becomes available. Learning (possibly dynamic and out-of-equilibrium) causal models from a continuous stream of data is thus extremely challenging, especially when data comes from multiple disparate sources and is collected under different conditions and study designs.

The field of continual learning is poised to mitigate these shortcomings. Although there has been work on transferring causal information across domains and populations (Pearl 2014, Lee 2020), a challenging assumption of sufficient background knowledge on what features are shared across the domains is made.
Continual learning can aid causal learning tools by mitigating the fragility of models to data distribution shifts with partially available information
as well as provide benefits to learning from the temporal structure of the stream of data. 

In turn, causal tools present an opportunity to aid continual learning algorithms through improving their capability of discovering and describing the underlying system beyond the statistical relationships learned from a stream of data received from the environment. The latter presents an opportunity to further improve not only a continual model's explainability and effectiveness in decision making, but also our human understanding of continual techniques.

However, despite a few recent attempts (Javed 2020, Chu 2020, Gong 2022), it is presently not clear how to incorporate the advances of causal inference with those of continual learning and vice versa. The interface remains a relatively unexplored research area. In this bridge program, we aim to take the first steps towards a unified treatment. By placing these disciplines under a conceptual and theoretical umbrella, their intersection will help catalyze advances in prediction and explanation in machine learning, thus taking another step towards building general-purpose artificial intelligence. 

