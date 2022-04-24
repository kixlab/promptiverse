---
layout: default
---

## Abstract
Online learners are hugely diverse with varying prior knowledge, but most instructional videos online are created to be one-size-fits-all. Thus, learners may struggle to understand the content by only watching the videos. Providing scaffolding prompts can help learners overcome these struggles through questions and hints that relate different concepts in the videos and elicit meaningful learning. However, serving diverse learners would require a spectrum of scaffolding prompts, which incurs high authoring effort. In this work, we introduce <span style="color:{{site.syscolor}}">Promptiverse</span>, an approach for generating diverse, multi-turn scaffolding prompts at scale, powered by numerous tra- versal paths over knowledge graphs. To facilitate the construction of the knowledge graphs, we propose a hybrid human-AI annotation tool, <span style="color:{{site.syscolor2}}"> Grannotate</span>. In our study (N=24), participants produced 40 times more on-par quality prompts with higher diversity, through <span style="color:{{site.syscolor}}">Promptiverse</span> and <span style="color:{{site.syscolor2}}"> Grannotate</span>, compared to hand-designed prompts. <span style="color:{{site.syscolor}}">Promptiverse</span> presents a model for creating diverse and adaptive learning experiences online.

------

## Process of Generating Scaffolding Prompts

{: .sys-img}
![Four components: Lecture video, Transcript, Knowledge graph, Scaffolding Prompts](/assets/img/teaser_vk.png)

With <span style="color:{{site.syscolor}}">Promptiverse</span>, lecture designers can create a large number of diverse scaffolding prompts by extracting rich knowledge graphs from a video script. These knowledge graphs can be efficiently extracted with the help of <span style="color:{{site.syscolor2}}"> Grannotate</span>, a human-AI hybrid graph annotation tool. <span style="color:{{site.syscolor}}">Promptiverse</span> generates scaffolding prompts by traversing knowledge graphs in a way that is guided by the learning patterns of Ausubel’s theory.

------

## <span style="color:{{site.syscolor}}">Promptiverse</span> : Generating Prompts with Knowledge Graph

<span style="color:{{site.syscolor}}">Promptiverse</span> codifies 1) how a single prompt can be generated, 2) how a dyad of prompts can be generated with single prompts while keeping the coherency in prompt content, and 3) how multi-turn prompts can be formulated with dyads of prompts in pedagogically meaningful ways. 

### Generating a Single Prompt

Based on how knowledge elements are elicited or provided, a single triplet turns into three versions of single prompts.

{: .sys-img}
![Each graph for Provide-all, Elicit-entity, and Elicit-relation.](/assets/img/single_prompt.png)

In *provide-all* (left), both knowledge entities and the connecting relation are given in the prompt. In *elicit-entity* (middle), one of the entities is asked while giving the other entity and the relation as hints. *Elicit-relation* (right) asks about the relation while giving both entities as hints.

### Generating a Dyad of Prompts

For more effective prompting, multiple prompts can be combined into one coherent multi-turn scaffolding prompt. To create such multi-turn prompts, Promptiverse finds two prompts that share an entity, as that entity would bridge the context between the prompts. Another rule is to prevent eliciting already provided or elicited knowledge elements again, as asking about already mentioned information could be pointless. 


{: .sys-img}
![Two same graphs for a) Chaining with an entity and b) Not eliciting already shown knowledge.](/assets/img/dyad.png)


### Generating Educationally Effective Prompts

To expand dyads of prompts to educationally meaningful prompts, we devised four types of multi-turn scaffolding prompting mechanisms inspired by Ausubel’s theory about **superordinate, correlative, derivative, and combinatorial learning**. Ausbel’s theory proposes that meaningful learning is achieved when the instructional design considers the hierarchical relationships between prior knowledge and new knowledge.

{: .img-left}
![Three components: Deciduous tree, Maple, and Oak. Scaffolding prompts between lecturer and student.](/assets/img/superordinate.png)

{: .text-right}
This is an example of **superordinate prompting**. This type of learning happens when learners first learn subordinate knowledge entities (*Maple, Oak*) and then relate that to one superordinate entity (*Deciduous tree*). 

------

## <span style="color:{{site.syscolor2}}"> Grannotate</span>: Knowledge Graph Annotation System

To harness <span style="color:{{site.syscolor}}">Promptiverse</span>’s potential to scalably create prompts, we designed <span style="color:{{site.syscolor2}}"> Grannotate</span> to support the construction of the underlying knowledge graphs. 

{: .sys-img}
![Winder next to the design for a screen of a mobile application](/assets/img/interface-whole.png)

First, <span style="color:{{site.syscolor2}}"> Grannotate</span> has two representations of an annotated graph: overlaid on the transcript and a graph visualization. Our tool also shows how prompts would be created out of the annotation. Finally, to alleviate the burden of having many options for entities and relation classes, our tool provides following AI-driven recommendations: 1) entity recom- mendation, 2) relation existence recommendation, and 3) relation class recommendation.


------

## Results

To assess if <span style="color:{{site.syscolor}}">Promptiverse</span> and <span style="color:{{site.syscolor2}}">Grannotate</span> lead to the scalable generation of diverse scaffolding prompts, we conducted a series of experiments with 24 participants. 

First, we compared the quantity and quality of prompts from <span style="color:{{site.syscolor}}">Promptiverse</span>  with <span style="color:{{site.syscolor2}}">Grannotate</span> and those created manually. <span style="color:{{site.syscolor}}">Promptiverse</span>  with <span style="color:{{site.syscolor2}}">Grannotate</span> generated 40 times more prompts than manual designing while showing similar prompt quality according to the evaluation of two experts. Our approach also generated more diverse prompts including many different entities, relations, and their combinations. 

Secondly, we compared the quantity and quality of prompts generated from our approach, when users had or didn't have AI recommendations. Only the prompts created with recommendations were of comparable quality to manually designed prompts. While no significant difference was found in cognitive load, users with recommendations had a trend of having higher mental demand. As reported in interviews, AI recommendations could lead participants to self-reflect which might have increased the quality of prompts.

<!-- {: .center .quote}
T2M1: *"The recordings left behind by my group members helped clarify some of the misunderstandings or confusions that I had."*

{: .center .quote}
T1M2: *"Understanding [my team members] actions and intentions was fun somehow and made me work harder."*

{: .center .quote}
T5M2: *"With the voice recordings and the feature that showed what the users clicked on as they talked, it was as if we were working together."* -->


------

## CHI 2022 Paper (Camera-ready)

[Link to the PDF][1]

<!-- [ACM DL Link][2] -->

## Bibtex
<pre>
@inproceedings{10.1145/3491102.3502087,
  author = {Lee, Yoonjoo and Chung, John Joon Young and Kim, Tae Soo and Song, Jean Y. and Kim, Juho},
  title = {Promptiverse: Scalable Generation of Scaffolding Prompts Through Human-AI Hybrid Knowledge Graph Annotation},
  year = {2022},
  isbn = {9781450391573},
  publisher = {Association for Computing Machinery},
  address = {New Orleans, LA, USA},
  url = {https://doi.org/10.1145/3491102.3502087},
  doi = {10.1145/3491102.3502087},
  booktitle = {Proceedings of the 2022 CHI Conference on Human Factors in Computing Systems},
  numpages = {18},
  keywords = {Scaffolding prompt, knowledge graph, human-AI hybrid annotation},
  location = {New Orleans, LA, USA},
  series = {CHI '22}
}
</pre>

------

{: .logos}
[![Logo of KIXLAB](/assets/img/kixlab_logo.png)](https://kixlab.org)
[![Logo of KAIST](/assets/img/kaist_logo.png)](https://kaist.ac.kr)

{: .center .acknowledgement}
This work was supported by the KAIST-NAVER Hypercreative AI Center, IITP grant funded by the Korea government, the DGIST Start-up Fund Program of the Ministry of Science and ICT(2021070007), and the NRF.

[1]:https://kixlab.github.io/website-files/2022/chi2022-promptiverse-paper.pdf
<!-- [2]:https://dl.acm.org/doi/10.1145/3411764.3445686 -->
