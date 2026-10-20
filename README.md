🛡️ Sentry — AI-Powered Scam Detection

Real-time protection against digital arrest scams, financial fraud, and AI-generated voice impersonation.

Sentry is an AI-powered scam detection system designed to protect older adults and less tech-confident individuals from fraudulent calls. It analyses conversations for suspicious behaviour, verifies callers’ claims using official sources, and provides timely warnings to help users make safer decisions.

🚨 Problem Statement

Scammers exploit fear, urgency, and trust to manipulate victims into sharing sensitive information or transferring money. Traditional caller ID applications cannot reliably detect scams based on conversational context or verify every claim made by a caller.

Sentry addresses this gap by analysing what a caller says, identifying pressure tactics, and verifying claims before the victim acts.

💡 Our Solution

Sentry follows a three-step approach:

* Detect: Analyses live or recorded audio for threats, urgency, secrecy, suspicious payment requests, and potential AI-generated voices.
* Verify: Uses TinyFish to check extracted claims against official websites, contact details, and public scam advisories.
* Protect: Displays explainable risk warnings, provides verified contact details, and optionally alerts a trusted family member with consent.

✨ Key Features

* Real-Time Scam Detection: Identifies suspicious conversational patterns and requests for money or OTPs.
* Call Recording Analysis: Analyses uploaded call recordings and WhatsApp voice notes to generate scam reports.
* Claim Verification: Checks callers’ claims against official sources and flags mismatches.
* AI Voice Detection: Estimates the likelihood of synthetic voice generation as an additional risk signal.
* Risk Assessment: Classifies potential threats as Low, Medium, High, or Critical.
* Trusted-Family Alerts: Sends optional alerts when high-risk activity is detected.
* Privacy-Conscious Processing: Keeps raw audio and transcripts on-device; only extracted claims are sent for web verification.

⚙️ How It Works

1. Audio is processed and converted into text.
2. AI models analyse conversational patterns and assess voice authenticity.
3. Relevant claims, such as institution names and phone numbers, are extracted.
4. TinyFish retrieves information from official sources to support claim verification.
5. A risk engine combines the available signals to generate an explainable risk score.
6. The user receives a warning and guidance on verifying the caller independently.

🧠 Technology Stack

Component	Technologies
Speech Processing	Whisper, Silero VAD
AI & NLP	PyTorch, IndicBERT/mBERT, LLMs
Web Verification	TinyFish Search, Fetch, Agent
Backend	FastAPI, WebSockets, Redis, PostgreSQL
Frontend	React
Notifications	Push and WhatsApp alerts

The technologies listed represent the proposed system architecture; actual implementation may vary.

🔒 Privacy & Safety

Sentry is designed with privacy and responsible detection in mind:

* Raw audio and transcripts are not sent to TinyFish.
* Voice-clone detection is treated as a supporting signal, not definitive proof of fraud.
* Claim verification relies on official sources wherever possible.
* Family alerts are optional and consent-based.
* Risk warnings explain the suspicious patterns or claim mismatches detected.

🎯 Target Users

* Older adults vulnerable to impersonation scams.
* People less familiar with digital fraud tactics.
* Individuals receiving frequent calls from unknown numbers.
* Families and caregivers seeking additional protection for loved ones.

🌍 Expected Impact

Sentry aims to create a crucial pause between a scammer’s manipulation and a victim’s financial decision. By combining conversational analysis, voice-authenticity signals, and web-based claim verification, it helps users recognise suspicious calls and verify information before taking action.

🚀 Future Scope

* Improved detection across Indian languages and regional accents.
* Enhanced integration with mobile calling systems.
* More robust detection of AI-generated voices.
* Expanded scam intelligence using verified public advisories.
* Testing across genuine urgent calls and different scam scenarios to reduce false alarms.

⸻

Sentry — Detect the threat. Verify the claim. Protect the person.
