---
title: "AMREx: AMR for Explainable Fact Verification"
event: "The seventh Fact Extraction and VERification Workshop (FEVER) - EMNLP 2024"
location: "Miami, Florida, USA"
date: 2024-11-02
type: "Presentation"
# slides: "#"
video: https://underline.io/lecture/107030-amrex-amr-for-explainable-fact-verification
layout: talk
author_profile: true
---
With the advent of social media networks and the vast amount of information circulating through them, automatic fact verification is an essential component to prevent the spread of misinformation. It is even more useful to have fact verification systems that provide explanations along with their classifications to ensure accurate predictions. To address both of these requirements, we implement AMREx, an Abstract Meaning Representation (AMR)-based veracity prediction and explanation system for fact verification using a combination of Smatch, an AMR evaluation metric to measure meaning containment and textual similarity, and demonstrate its effectiveness in producing partially explainable justifications using two community standard fact verification datasets, FEVER and AVeriTeC. AMREx surpasses the AVeriTec baseline accuracy showing the effectiveness of our approach for real-world claim verification. It follows an interpretable pipeline and returns an explainable AMR node mapping to clarify the system’s veracity predictions when applicable. We further demonstrate that AMREx output can be used to prompt LLMs to generate natural-language explanations using the AMR mappings as a guide to lessen the probability of hallucinations.