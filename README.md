# Sentry

**Detect the threat. Verify the claim. Protect the person.**

Sentry is an AI-powered scam detection tool that warns people during suspicious calls, before they share sensitive details or send money. It is built for older adults and less tech-confident users, who are the most common targets of fake police calls, bank impersonation, "digital arrest" threats and AI-cloned voices.

Team: Binary Biryani | Track: AI/ML | Team Leader: Harleen Kaur

---

## The Problem

Most phone scams work because of pressure, not technology. The caller poses as an official, threatens arrest or financial loss, demands immediate action and tells the victim not to talk to anyone. Under that pressure, people comply before they can cross-check.

Existing tools don't solve this well:

- **Caller ID apps** only flag known numbers. They miss numbers a victim dials themselves, and they ignore what is actually said on the call.
- **Official advice** such as "never trust unknown callers" is hard to follow in the moment, and official helpline numbers are often buried several clicks deep.

Victims need a clear warning during the conversation, not after the money has left their account.

## What Sentry Does

Sentry works in three steps.

**1. Detect**
Sentry analyses a call for scam patterns: claims of authority, threats, urgency, requests for secrecy, and demands for money or OTPs. It also estimates whether a voice may be AI-generated.

**2. Verify**
Claims made by the caller, such as the institution name, phone number or UPI ID, are checked against official websites and public scam advisories using TinyFish.

**3. Protect**
The user gets a plain-language warning with the reasons behind it, the verified official number to call back, and, if they choose, an alert sent to a trusted family member.

## Three Ways to Use It

| Mode | When to use it | What you get |
|---|---|---|
| **Live Protection** | A suspicious call is happening now | Real-time transcription and a rolling risk score as the conversation develops |
| **Analyse a Recording** | You have a call recording or WhatsApp voice note | A full report with timestamped red flags, scam type and a final verdict |
| **Check a Caller** | You got a call but didn't record it | Enter the caller's claimed identity, number, UPI ID or link, and what they asked you to do. Sentry checks the details and returns a risk score with reasons |

## Key Features

- **Scam pattern detection** across Hindi, English and Hinglish, tracking how a call escalates from authority to fear, urgency, secrecy and payment
- **Claim verification** against official sources, with mismatches flagged clearly
- **Explainable risk levels** (Low, Medium, High, Critical), always shown with reasons
- **AI voice score** as a supporting signal, not a final verdict
- **Trusted-family alerts**, optional and consent-based
- **Emergency guidance** after a loss: call 1930, block the card and file a complaint

## How It Works

1. Audio is captured and converted to text, with voice activity detection to isolate speech.
2. A multilingual classifier analyses the conversation for scam patterns, while a separate model scores voice authenticity.
3. An LLM extracts checkable claims such as institution names, phone numbers, UPI IDs and links.
4. TinyFish Search, Fetch and Agent verify those claims against official sources and public advisories.
5. A risk engine combines all signals into one risk level with reasons.
6. The user receives a warning and clear steps to verify the caller independently.

## Tech Stack

| Area | Technologies |
|---|---|
| Speech and audio | Whisper, Silero VAD |
| AI and NLP | PyTorch, IndicBERT / mBERT, LLM for claim extraction |
| Web verification | TinyFish Search, Fetch, Agent |
| Backend | FastAPI, WebSockets, Redis, PostgreSQL |
| Frontend | React |
| Notifications | Push and WhatsApp alerts |

*This reflects the proposed architecture. The final implementation may differ.*

## Privacy and Safety

- Raw audio and transcripts are not sent to TinyFish. Only the extracted claims (institution name, phone number, UPI ID, link and claim type) are sent for verification.
- Voice-clone detection is one signal among several. It is never treated as proof of fraud on its own.
- Verification relies on official sources wherever possible.
- Family alerts are optional and require the user's consent.
- Every warning explains which patterns or claim mismatches triggered it.

## Who It's For

- **Primary users:** older adults, people less familiar with digital fraud, and anyone who frequently receives unknown calls
- **Secondary users:** families and caregivers, and bank fraud and cybercrime teams through evidence reports

## Expected Impact

Sentry aims to create a pause between a scammer's pressure and a victim's decision. By combining conversation analysis, voice signals and live claim verification, it helps people recognise a suspicious call and confirm the facts before they act.

We plan to measure this through scam-detection accuracy, false-positive rate, warning latency, claim-verification accuracy and user comprehension.

## Prototype Scope

A working prototype can demonstrate detection without direct access to ordinary cellular calls. Sentry is tested through prerecorded scam audio, live microphone or simulated call audio, and manual caller checks. Validation uses scam conversations, genuine urgent calls and AI-generated voice samples, to measure accuracy and keep false alarms low.

## Future Scope

- Better detection across more Indian languages and regional accents
- Closer integration with mobile calling systems
- More robust detection of AI-generated voices
- A scam-script library kept current through human-reviewed public advisories
- Wider testing on genuine urgent calls to further reduce false alarms

---

**Sentry** | Detect the threat. Verify the claim. Protect the person.
