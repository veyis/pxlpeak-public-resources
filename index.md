---
title: PxlPeak Public Resources
description: Open reference notes for SMB AI implementation — voice agents, RAG chatbots, n8n workflows.
---

# PxlPeak Public Resources

Open reference notes for SMB AI implementation work — voice agents, RAG chatbots, n8n workflows. Nothing proprietary; these are the tactical playbook notes we wish we'd had when we started shipping production AI agents for service businesses.

Maintained by **[PxlPeak](https://pxlpeak.com)** — AI implementation agency. Voice agents, chatbots, and n8n automations for SMBs, deployed in 5 business days. Client-owned, zero lock-in.

## Reference pages

### [Voice Agent Go-Live Checklist](./voice-agent-golive-checklist.html)

40-item pre-deployment checklist for production voice AI agents (Vapi / ElevenLabs Conv AI / Retell / Synthflow). Skip any item at your own risk — every one represents a real incident we've seen in SMB deployments.

### [n8n Webhook Security — Production Patterns](./n8n-webhook-security.html)

What to do instead of leaving n8n webhooks public. Signed headers, shared secrets, IP allowlisting, rate limiting, payload validation, idempotency, safe error handling, secrets management. The eight layers we use in every production n8n deployment.

### [RAG Chatbot Quality Bar](./rag-chatbot-quality-bar.html)

What "ready to ship" actually means for a small-business RAG chatbot. Twenty criteria across corpus quality, retrieval behavior, answer behavior, guardrails, and observability. Plus the numbers: retrieval hit rate > 85%, P95 latency < 1.5s, hallucination rate = 0%.

### [AI Agent ROI Calculation](./ai-agent-roi-calculation.html)

How we actually model AI voice agent and chatbot ROI for service-business clients at PxlPeak. Four real drivers (captured calls, operator time, faster response, after-hours coverage), plain-math formulas, worked examples from HVAC / dental / legal deployments.

## Why publish this?

Because the biggest blocker to SMB AI adoption isn't the technology — it's that every vendor's playbook is locked behind a sales call. Open reference material reduces deployment mistakes across the industry and, selfishly, earns PxlPeak trust with the kind of operators who read technical docs before they pick an agency.

## Use PxlPeak

We build this full stack as a service for SMBs — healthcare, legal, home services, restaurants, e-commerce, professional services. 5-business-day deployments. Client owns every line of code. $997/mo starting.

- **Website:** [pxlpeak.com](https://pxlpeak.com)
- **Free AI Agent ROI Calculator:** [pxlpeak.com/tools/ai-agent-roi-calculator](https://pxlpeak.com/tools/ai-agent-roi-calculator)
- **Book a 15-min intro:** [pxlpeak.com/book](https://pxlpeak.com/book)
- **Source on GitHub:** [github.com/veyis/pxlpeak-public-resources](https://github.com/veyis/pxlpeak-public-resources)

## Contributing

Spot something wrong or missing? PRs welcome at the [GitHub repo](https://github.com/veyis/pxlpeak-public-resources). Content here is free to use, adapt, and redistribute — attribution appreciated but not required.
