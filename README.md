# ml-design-doc

A template for design docs for machine learning systems based on this [post](https://eugeneyan.com/writing/ml-design-docs/).

Note: This template is a guideline / checklist and is **not meant to be exhaustive**. The intent of the design doc is to help you think better (about the problem and design) and get feedback. Adopt whichever sections—and add new sections—to meet this goal. View other templates, examples [here](#other-templates-examples-etc).

---
## 1. Overview

A summary of the doc's purpose, problem, solution, and desired outcome, usually in 3-5 sentences.

## 2. Motivation
Why the problem is important to solve, and why now.

## 3. Success metrics
Usually framed as business goals, such as increased customer engagement (e.g., CTR, DAU), revenue, or reduced cost.

## 4. Requirements & Constraints
Functional requirements are those that should be met to ship the project. They should be described in terms of the customer perspective and benefit. (See [this](https://eugeneyan.com/writing/ml-design-docs/#the-why-and-what-of-design-docs) for more details.)

Non-functional/technical requirements are those that define system quality and how the system should be implemented. These include performance (throughput, latency, error rates), cost (infra cost, ops effort), security, data privacy, etc.

Constraints can come in the form of non-functional requirements (e.g., cost below $`x` a month, p99 latency < `y`ms)

### 4.1 What's in-scope & out-of-scope?
Some problems are too big to solve all at once. Be clear about what's out of scope.

## 5. Methodology

### 5.1. Problem statement

How will you frame the problem? For example, fraud detection can be framed as an unsupervised (outlier detection, graph cluster) or supervised problem (e.g., classification).

### 5.2. Data

What data will you use to train your model? What input data is needed during serving?

### 5.3. Techniques

What machine learning techniques will you use? How will you clean and prepare the data (e.g., excluding outliers) and create features?

### 5.4. Experimentation & Validation

How will you validate your approach offline? What offline evaluation metrics will you use?

If you're A/B testing, how will you assign treatment and control (e.g., customer vs. session-based) and what metrics will you measure? What are the success and [guardrail](https://medium.com/airbnb-engineering/designing-experimentation-guardrails-ed6a976ec669) metrics?

### 5.5. Human-in-the-loop

How will you incorporate human intervention into your ML system (e.g., product/customer exclusion lists)?

## 6. Implementation

### 6.1. High-level design

![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Data-flow-diagram-example.svg/1280px-Data-flow-diagram-example.svg.png)

Start by providing a big-picture view. [System-context diagrams](https://en.wikipedia.org/wiki/System_context_diagram) and [data-flow diagrams](https://en.wikipedia.org/wiki/Data-flow_diagram) work well.

### 6.2. Infra

How will you host your system? On-premise, cloud, or hybrid? This will define the rest of this section

### 6.3. Performance (Throughput, Latency)

How will your system meet the throughput and latency requirements? Will it scale vertically or horizontally?

### 6.4. Security

How will your system/application authenticate users and incoming requests? If it's publicly accessible, will it be behind a firewall?

### 6.5. Data privacy

How will you ensure the privacy of customer data? Will your system be compliant with data retention and deletion policies (e.g., [GDPR](https://gdpr.eu/what-is-gdpr/))?

### 6.6. Monitoring & Alarms

How will you log events in your system? What metrics will you monitor and how? Will you have alarms if a metric breaches a threshold or something else goes wrong?

### 6.7. Cost
How much will it cost to build and operate your system? Share estimated monthly costs (e.g., EC2 instances, Lambda, etc.)

### 6.8. Integration points

How will your system integrate with upstream data and downstream users?

### 6.9. Risks & Uncertainties

Risks are the known unknowns; uncertainties are the unknown unknows. What worries you and you would like others to review?

## 7. Appendix

### 7.1. Alternatives

What alternatives did you consider and exclude? List pros and cons of each alternative and the rationale for your decision.

### 7.2. Experiment Results

Share any results of offline experiments that you conducted.

### 7.3. Performance benchmarks

Share any performance benchmarks you ran (e.g., throughput vs. latency vs. instance size/count).

### 7.4. Milestones & Timeline

What are the key milestones for this system and the estimated timeline?

### 7.5. Glossary

Define and link to business or technical terms.

### 7.6. References

Add references that you might have consulted for your methodology.

---
## Other templates, examples, etc
- [A Software Design Doc](https://www.industrialempathy.com/posts/design-doc-a-design-doc/) `Google`
- [Design Docs at Google](https://www.industrialempathy.com/posts/design-docs-at-google/) `Google`
- [Product Spec of Emoji Reactions on Twitter Messages](https://docs.google.com/document/d/1sUX-sm5qZ474PCQQUpvdi3lvvmWPluqHOyfXz3xKL2M/edit#heading=h.554u12gw2xpd) `Twitter`
- [Design Docs, Markdown, and Git](https://caitiem.com/2020/03/29/design-docs-markdown-and-git/) `Microsoft`
- [Technical Decision-Making and Alignment in a Remote Culture](https://multithreaded.stitchfix.com/blog/2020/12/07/remote-decision-making/) `Stitchfix`
- [Design Documents for Chromium](https://www.chromium.org/developers/design-documents) `Chromium`
- [PRD Template](https://works.hashicorp.com/articles/prd-template) and [RFC Template](https://works.hashicorp.com/articles/rfc-template) (example RFC: [Manager Charter](https://works.hashicorp.com/articles/manager-charter)) `HashiCorp`
- [Pitch for To-Do Groups and Group Notifications](https://basecamp.com/shapeup/1.5-chapter-06#examples) `Basecamp`
- [The Anatomy of a 6-pager](https://writingcooperative.com/the-anatomy-of-an-amazon-6-pager-fc79f31a41c9) and an [example](https://docs.google.com/document/d/1LPh1LWx1z67YFo67DENYUGBaoKk39dtX7rWAeQHXzhg/edit) `Amazon`
- [Writing for Distributed Teams](http://veekaybee.github.io/2021/07/17/p2s/), [How P2 Changed Automattic](https://ma.tt/2009/05/how-p2-changed-automattic/) `Automattic`
- [Writing Technical Design Docs](https://medium.com/machine-words/writing-technical-design-docs-71f446e42f2e), [Writing Technical Design Docs, Revisited](https://medium.com/machine-words/writing-technical-design-docs-revisited-850d36570ec) `AWS`
- [How to write a good software design doc](https://www.freecodecamp.org/news/how-to-write-a-good-software-design-document-66fcf019569c/) `Plaid`

Contributions [welcome](https://github.com/eugeneyan/ml-design-docs/pulls)!
