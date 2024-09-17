---
layout: default
title: "AI Readiness Governance Framework"
---

This document describes a simple AI system consisting of a Large Language Model with Retrieval Augmented Generation (RAG) using an external SaaS for inference. This is being used as a vehicle for developing a governance framework for on-boarding GenAI technology, and should be considered an early stage draft document.

## Introduction

The recent advances in AI (and more specifically Generative AI) are poised to have a disruptive impact across both our business and home lives. The rapid advances (that are showing no sign of slowing) are leading to a wealth or potential that touches upon the products we (within financial services) offer to clients, our personal productivity as well as the operational aspects of our business. Very few technologies in the past have had such a broad 'reach'.

There are certainly challenges and issues with the current technology (hallucinations, prompt injections), but things are moving at pace, and the technology challenges we see today may not exist tomorrow.

There is a very strong desire to on-board, trial, experiment and release products using this technology across the FINOS membership and broader FS community. However, as an industry we have some unique challenges.

All banks have mature processes for on-boarding technology, however, (Generative) AI presents some new challenges that the existing processes may not be well-suited to addressing. Without going into the details, there is much work needed to allow the 'safe' use of AI (where safety considers both the customer and the bank) and ultimately allow FS organisations to rapidly adopt new technologies as they emerge.

## Initial scope - RAG-based Q&A

While the ultimate goal is to develop a comprehensive governance framework that can accommodate a wide variety of use cases, starting with a narrowly focused, well-defined initial scope offers several advantages. By selecting a common, high-impact use case that financial organizations frequently encounter, we can create immediate value and demonstrate the effectiveness of our approach. This smaller, more manageable scope will allow for a quicker implementation and iteration process, enabling us to refine our framework based on real-world experience. Additionally, focusing on a use case that can be open-sourced not only fosters collaboration but also ensures that the framework is adaptable and beneficial to a broader community. This initial effort will serve as a foundation for developing a robust governance structure that can be scaled and expanded to cover a wide range of applications in the future.

The initial scope is outlined as follows:

 - An architecture based on a Generative AI Large Language Model.
 - System composed of a SaaS inference endpoint external to the organization.
 - Usage of Retrieval Augmented Generation (RAG), to provide a knowledge base custom to the organization.
 - Users are internal to the organization. They interact with the system through a UI and are responsible for how they use the provided information.

Out of scope (for now):

 - Pre-trained model (open source or not) that the organization deploys on its own infrastructure.
 - Fine tunning of a model (be it open source, or SaaS).
 - AI agents collaborating.
 - User interacting with the model is external to the organization.
 - User is not first responsible for action, but the AI model, being it completely independent, or having light supervision.
 - Most safety/bias consideration are out of scope for the first version of the governance framework, but will be considered later as it is one of the objectives for the group in general.
 - Small models that are very specialized, and are updated continuosly depending on the data being feeded (example models for organizing cache in a bigger system).

Assumptions: 

- We can rely upon the operational controls in place in the organisaton already. Financial industry standard existing governance is assumed for the infrastructure, supply chain, and application code.
- The system has an auditor, and its result/actions has potential legal implications.
- Users of this system have responsibility for their actions.
- Mitigation steps for ethical and responsibility concerns are the remit of the application developer and its data's classifications.
- The system's metadata/metrics/logs to audit the accuracy and bias of this system are known and have an existing process.
- Carbon outputs and system cost are intertwined, but these are the responsibility of app/system developers.

![LLM using RAG threats](llm_rag_security.svg)

## Metadata

Each Threat or Control has a status which indicates its current level of maturity:

<table>
  <thead>
    <tr>
      <th>Status</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    {% for status in site.document_status %}
    <tr>
      <td>{{ status.name }}</td>
      <td>{{ status.description }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>


## Contents

### Threats
{% assign sorted_threats = site.threats | sort: 'sequence' %}
<table>
  <thead>
    <tr>
      <th>ID</th>
      <th>Status</th>
      <th>Title</th>
    </tr>
  </thead>
  <tbody>
  {% for threat in sorted_threats %}
    <tr>
      <td><a href="#TR-{{ threat.sequence }}">TR-{{ threat.sequence }}</a></td>
      <td>{{ threat.doc-status }}</td>
      <td>{{ threat.title }}</td>
    </tr>
  {% endfor %}
  </tbody>
</table>

### Controls
{% assign sorted_controls = site.controls | sort: 'sequence' %}
<table>
  <thead>
    <tr>
      <th>ID</th>
      <th>Status</th>
      <th>Title</th>
    </tr>
  </thead>
  <tbody>
  {% for control in sorted_controls %}
    <tr>
      <td><a href="#CT-{{ control.sequence }}">CT-{{ control.sequence }}</a></td>
      <td>{{ control.doc-status }}</td>
      <td>{{ control.title }}</td>
    </tr>
  {% endfor %}
  </tbody>
</table>

## Threats

{% for threat in sorted_threats %}
<h3 id="TR-{{ threat.sequence }}">TR-{{ threat.sequence }} - {{ threat.title }}</h3>
<dl>
  <dt>Document Status</dt>
  <dd>{{ threat.doc-status }}</dd>
  <dt>Threat Type</dt>
  <dd>{{ threat.type | join: ', ' }}</dd>
</dl>
<p>{{ threat.content | markdownify }}</p>
{% endfor %}

## Controls

{% for control in sorted_controls %}
<h3 id="CT-{{ control.sequence }}">CT-{{ control.sequence }} - {{ control.title }}</h3>
<dl>
  <dt>Document Status</dt>
  <dd>{{ control.doc-status }}</dd>
  <dt>Control Type</dt>
  <dd>{{ control.type | join: ', ' }}</dd>
  <dt>Mitigates</dt>
    <dd>
      <ul>
        {% for mitigant in control.mitigates %}
        <li><a href="#{{ mitigant | upcase }}">{{ mitigant | upcase }}</a></li>
        {% endfor %}
      </ul>
    </dd>
</dl>
<p>{{ control.content | markdownify }}</p>
{% endfor %}

