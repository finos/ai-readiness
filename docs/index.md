---
layout: default
title: "AI Readiness Governance Framework"
---

*Distributed under the [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/deed.en).*

## Introduction

The rapid advancements in Artificial Intelligence (AI), particularly Generative AI, are set to revolutionize both business operations and personal lives. In the financial services sector, these innovations present immense opportunities that span product offerings, client interactions, employee productivity, and organizational operations. Few technologies have promised such a broad and transformative impact.

However, these advancements also bring significant challenges. Issues like hallucinations, prompt injections, and model unpredictability introduce unique complexities to safely integrate and deploy AI technologies. The pace of technological change means that today's solutions may become obsolete tomorrow, necessitating a flexible yet robust governance approach.

Financial institutions (in particular) are eager to onboard, experiment with, and deploy AI technologies to stay both competitive and innovative. Yet, the risk landscape and regulatory environment of the financial services industry necessitates proper governance. Existing processes/frameworks may not be adequately equipped to address the novel challenges posed by AI, particularly Generative AI. Therefore, there is a critical need for an adaptive governance framework that promotes the safe, trustworthy, and compliant adoption of


## Contents

{% assign sorted_risks = site.risks | sort: 'sequence' %}
{% assign sorted_migitations = site.mitigations | sort: 'sequence' %}

## Risks

{% for risk in sorted_risks %}
<h3 id="RI-{{ risk.sequence }}">FINOS-AIR-RI-{{ risk.sequence }} - {{ risk.title }}</h3>
<dl>
  <dt>Document Status</dt>
  <dd>{{ risk.doc-status }}</dd>
  <dt>Threat Type</dt>
  <dd>{{ risk.type | join: ', ' }}</dd>
</dl>
<p>{{ risk.content | markdownify }}</p>
{% endfor %}

## Mitigations

{% for mitigation in sorted_migitations %}
<h3 id="FINOS-AIR-MI-{{ mitigation.sequence }}">FINOS-AIR-MI-{{ mitigation.sequence }} - {{ mitigation.title }}</h3>
<dl>
  <dt>Document Status</dt>
  <dd>{{ mitigation.doc-status }}</dd>
  <dt>Mitigation Type</dt>
  <dd>{{ mitigation.type | join: ', ' }}</dd>
  <dt>Mitigates</dt>
    <dd>
      <ul>
        {% for mitigant in mitigation.mitigates %}
        <li><a href="#{{ mitigant | upcase }}">{{ mitigant | upcase }}</a></li>
        {% endfor %}
      </ul>
    </dd>
</dl>
<p>{{ mitigation.content | markdownify }}</p>
{% endfor %}

