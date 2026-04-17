---
title: "Voice Agent Go-Live Checklist — 40 Production Items (Vapi / ElevenLabs / Retell)"
description: "Production pre-deployment checklist for AI voice agents. Intent, prompt, integration, telephony, observability, and human-handoff checks. Used for every SMB voice deployment at PxlPeak."
keywords: "voice ai agent, vapi, elevenlabs, retell, production checklist, smb voice agent, ai deployment"
---

# Voice Agent Go-Live Checklist

Pre-deployment checklist for a production voice AI agent (Vapi / ElevenLabs Conv AI / Retell / Synthflow). Used at [PxlPeak](https://pxlpeak.com) for every SMB voice deployment. 40 items across 6 categories.

Skip any item at your own risk. Every one of these represents a real incident we've seen.

---

## 1. Intent & scope

- [ ] Written "what this agent does / does not do" one-pager approved by the business owner
- [ ] Top 10 expected user intents documented with example phrasings
- [ ] Escalation path defined: when does the agent transfer to a human? What numbers? What hours?
- [ ] "I don't know" behavior specified — how does the agent handle out-of-scope questions?
- [ ] HIPAA / PCI / other compliance scope confirmed in writing with the client before going live

## 2. Prompt & behavior

- [ ] System prompt version-controlled in a git repo (not just pasted into the vendor console)
- [ ] Business hours logic handled explicitly — the agent should not schedule Sundays for a Monday-Friday business
- [ ] Timezone handling is explicit and tested (naive clients assume America/New_York)
- [ ] Agent identity is consistent: same name every time, same voice, same tone
- [ ] Profanity and hostile-user handling tested with at least 5 adversarial prompts
- [ ] Hallucination guardrails: if the agent doesn't know a business detail, it says so and offers to connect a human

## 3. Integrations

- [ ] Booking system webhook end-to-end tested with real bookings (not mocks)
- [ ] CRM write verified — new leads actually land in the CRM, not just in a log file
- [ ] SMS follow-up tested on a real phone (twilio sandbox ≠ production)
- [ ] Payment collection (if applicable) runs in a sandbox environment for go-live week one
- [ ] Failure path for every integration: what happens if the CRM API is down mid-call?

## 4. Telephony & voice

- [ ] Phone number provisioned and verified to receive calls (test from 3 different carriers)
- [ ] Outbound caller ID shows the business name, not "Unknown" or the vendor default
- [ ] Voice latency tested below 1.5 seconds (anything above 2s feels broken)
- [ ] Voice and accent match the business's customer base — a Southern plumber should not have a British accent
- [ ] Call recording disclosure enabled where legally required (CA, FL, IL, MD, MA, MT, NH, PA, WA at minimum)
- [ ] Barge-in (user interrupting the agent) works cleanly
- [ ] Silence timeout is tuned — 8s default is often too long for impatient callers

## 5. Observability

- [ ] Every call logged with transcript, duration, outcome, and cost
- [ ] Failure alerts wired to Slack or SMS — someone gets paged if the agent is down for 5 min
- [ ] Weekly review dashboard in place (call volume, resolution rate, escalation rate, cost/call)
- [ ] Client has read-only access to their own agent's dashboard
- [ ] Cost ceiling alerts set (at PxlPeak, typically $X/day with auto-page)

## 6. Human handoff & trust

- [ ] A human answers when the agent can't — voicemail is not an acceptable fallback
- [ ] The client can listen to 5 random call recordings per week without asking us
- [ ] A "kill switch" exists: the client can disable the agent and route all calls to a human in under 60 seconds
- [ ] First 7 days of production, a human reviews every transcript (not just sampled)
- [ ] Week-two review with the client: what worked, what didn't, what's getting edited

---

## Anti-patterns we no longer tolerate

- **"We'll monitor it manually for now."** Not a real observability plan. Set up alerts before go-live.
- **"Let's launch and iterate."** Fine in principle. Not fine when the client's main business line is the phone.
- **"The vendor dashboard is enough."** The vendor dashboard doesn't tell you if bookings are actually landing in the CRM.
- **"We'll train on call data over time."** You can train on data. You cannot train on customer trust that evaporated in week one.

---

Want this done for you? [PxlPeak](https://pxlpeak.com) ships production voice agents for SMBs in 5 business days. Fully owned by the client, no lock-in, $997/mo starting price. [Book a 15-min intro](https://pxlpeak.com/book).
