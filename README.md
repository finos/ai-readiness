<img src="https://github.com/finos/branding/blob/master/sig-logos/ai-readiness/Horizontal/2024_AIReadiness_Logo_Horizontal.svg" width="450">

# AI Readiness

Our goal is to mutually develop a governance framework that manages the on-boarding, development of, and running AI-based solutions within financial services organisations - allowing us all to unlock the potential of this disruptive technology in a safe, trustworthy and compliant way.
 
## Introduction

The recent advances in AI (and more specifically Generative AI) are poised to have a disruptive impact across both our business and home lives. The rapid advances (that are showing no sign of slowing) are leading to a wealth or potential that touches upon the products we (within financial services) offer to clients, our personal productivity as well as the operational aspects of our business. Very few technologies in the past have had such a broad 'reach'.

There are certainly challenges and issues with the current technology (hallucinations, prompt injections), but things are moving at pace, and the technology challenges we see today may not exist tomorrow.

There is a very strong desire to on-board, trial, experiment and release products using this technology across the FINOS membership and broader FS community. However, as an industry we have some unique challenges.

All banks have mature processes for on-boarding technology, however, (Generative) AI presents some new challenges that the existing processes may not be well-suited to addressing. Without going into the details, there is much work needed to allow the 'safe' use of AI (where safety considers both the customer and the bank) and ultimately allow FS organisations to rapidly adopt new technologies as they emerge.

## Goals and approach

The AI readiness group is at the very early formation stages, as a result, the goals and approach will likely evolve in the near-term. The current proposed approach to creating tangible value to members is:

 - **Focus on a subset of the problem** - with the breadth of AI technologies and applications, we cannot realistically tackle the problem all in one go. We’ll seek to identify a subset of the problem, driven by one or more specific use cases, in order to create a complete ‘vertical slice’ and deliver value early
 - **Leverage existing frameworks** -  financial services organisations already have robust frameworks in place for dealing with technology risk. We’ll look to leverage these framework, or approaches, where appropriate.
 - **Threat modelling** - for our selected use case(s), we’ll use threat modelling techniques to map out the challenge, then identify suitable mitigation 

## Membership

The AI Readiness is FINOS members only while we are in the formation stage. To join the group, please contact membersuccess@finos.org 

We use the following channels:
 - Group email distribution list: ai-readiness-private@lists.finos.org
 - Meetings follow Chatham House rules, with no formal minutes, however, actions and conclusions will be shared via the email distribution list.

Considering that there is a significant amount of work needed to build this framework, we have a smaller ‘core team’ who meet and work on this project outside of the fortnightly meetings. The current core team are:

 - Colin Eberhardt, CTO, Scott Logic (co-chair)
 - Ian Micallef, Citi, ICG Head of Developer Engineering  (co-chair)
 - Madhu Coimbatore, Morgan Stanley, Executive Director, AI Platform Development
 - Andrew Martin, CEO, ControlPlane
 - Oleg Blokhin, Executive General Manager, Provectus
 - Vicente Herrera Garcia, Principal Consultant, ControlPlane
 - James Heward, Principal Architect, Scott Logic
 - Mehak Mehta, AIMLOps Lead, Morgan Stanley

We welcome further core team members.

## Frequently Asked Questions

### What will the Governance Framework look like?
At a very high-level, the governance framework will allow you to characterise the risks or threats for a given AI-based system. The risks and threats are context dependent, in that they depend both on the architecture, and the use case (e.g. internal use has a very different risk profile to external). Once threats have been identified, the framework will provide suitable mitigations and controls.

The overall goal is that this framework should be deeply practical, allowing an organisation to demonstrate a methodical and thorough approach to on-boarding and developing AI-based solutions.

As well as publishing a governance framework, we will also publish guidance and educational materials that supports its usage.

### How will it be developed?
We’re taking a deeply practical use-case led approach. We’ll identify realistic use cases, threat model the system and identify mitigations and controls. As we expand our corpus of use cases, the framework will become more comprehensive.

### Are you building your own models or AI solutions?
No. 

### Will this framework help us on-board third-party AI services? 
Yes. In the future, it is likely that AI will become increasingly commoditised, with applications making use of externally hosted AI models (e.g. foundational models) which are accessible via APIs. This framework will certainly cover this type of architecture, as well as the more ‘traditional’ approach where an AI model is developer entirely in-house.

### Why do we need this framework? AI isn’t new?
Good question! AI has been widely used within financial services to great effect. Typically this has involved creating predictive (often numeric) AI models with closed datasets, under the guidance of experience data scientists.

However, in the past few years AI has become increasingly commoditised and democratised. The existing frameworks that financial services organisations have for managing AI models, model development and deployment aren’t compatible with the rapidly emerging (predominantly generative) AI models.

### Is this group just concerned with Generative AI?
The commoditisation of AI has been driven by Large Language Models (LLMs), which are a class of generative AI. While this group will not exclusively focus on GenAI, it is likely that many of the use cases we explore will be based on this technology.

### Is this group concerned with Responsible AI?
Yes, and no. We’re not going to tackle responsible or ethical AI ‘head on’. Rather, through analysing concrete use cases, we’ll tackle practical issues that could be considered as having an ethical or responsible dimension.

### What format will you publish the governance framework in?
Our intention is to make it as easy to consume as possible, as a result, we’ll likely take a web-first and interactive approach. We’ll certainly publish a PDF, however, we don’t believe that is the easiest way to consume this type of information.

### What about governance framework ‘x’, why aren’t you adopting that?
Currently we don’t believe there is an open framework that addresses the needs of the financial services community. If there were, it is likely it would have been adopted by now. 

However, there are a number of excellent frameworks that we feel this group can draw inspiration from. We do plan to undertake a review of existing materials and publish in this repo.

### Will this framework address the EU AI Act?
One of our key goals is to create a framework that makes it easy to follow whatever regional regulation are applied to the AI-based solutions you are building. We haven’t worked out exactly how to marry the two together just yet, and in all fairness, most of the AI-related regulations aren’t published yet. However, we will also consider pre-existing regulations that relate to AI-systems, for example data protection and sovereignty. 

---

## License

Copyright © 2023 Fintech Open Source Foundation

Distributed under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0).

SPDX-License-Identifier: [Apache-2.0](https://spdx.org/licenses/Apache-2.0)
