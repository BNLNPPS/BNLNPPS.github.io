---
title: ePIC streaming workflow orchestration testbed
abbrev: swf-testbed
software: swf-testbed
teams: wfm ml
common: true
layout: default
---

{% include softwarespecs.html %}

The ePIC streaming workflow orchestration testbed was esablished in 2025 to implement and evaluate a workflow management system capable of meeting the comprehensive requirements of ePIC workflow management, most particularly the streaming workflows that present new and challenging requirements arising from ePIC streaming computing model. The testbed is evaluating the distributed computing tools PanDA, iDDS and Rucio as the basis for the system, together with an agent infrastructure mediated by ActiveMQ messaging, and core services based on Django backed by Postgres, including a monitoring system, REST-based APIs to all system information, and MCP services providing LLM based interfaces.

Testbed overview talk: [Testbed talk at SRO-XIII, Dec 9 2025](https://docs.google.com/presentation/d/1KT8o6F7wclAvufqvJLRvZ3-TQ8MgDoR7Y6_xKVlq8Ew/edit?slide=id.gde3255a171_0_88#slide=id.gde3255a171_0_88)

[Testbed progress notes](https://docs.google.com/document/d/1PUoo-W6dCeOKsD4VubYTgSxBHBUb4D5dYfVy1oLYh7E/edit?tab=t.0) with links to recent talks

### References

- [swf-testbed in github](https://github.com/BNLNPPS/swf-testbed)
- [The ePIC Streaming Computing Model](https://zenodo.org/records/14675920)
- [ePIC workflow management requirements](https://www.overleaf.com/project/67bdf89a3d44a138da503dea)
- [iDDS: Intelligent Distributed Dispatch and Scheduling for Workflow Orchestration](https://arxiv.org/abs/2510.02930)]
- [PanDA: Production and Distributed Analysis System](https://link.springer.com/article/10.1007/s41781-024-00114-3), Comput Softw Big Sci 8, 4 (2024)