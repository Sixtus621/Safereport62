# SafeReport

An anonymous safeguarding reporting channel for exam and test centres, built as a proof of concept for the Andela Learning Community invention sprint (Safety, Reporting & Protection track).

## The problem

At exam centres, candidates, invigilators, and other staff often witness or experience things worth reporting — malpractice, harassment, safety hazards, coercion — but there is usually no channel to report them at all. People stay silent because reporting means giving up anonymity, because they don't trust it will go anywhere, or because there's simply no mechanism in the moment.

## Who this is for

- **Candidates and staff at exam centres** — the people who need a safe way to speak up
- **Safeguarding officers** — the people who need to receive, triage, and act on reports without a channel that dead-ends

## How it works

### Reporting (anonymous by default)
A reporter selects their exam centre, the type of concern, and describes what happened — no login, no name required. On submission they receive a private token (e.g. `AB3-K9F`). That token is the only way to check the report's status later; SafeReport never asks who they are unless they choose to leave contact details for follow-up.

### Checking status
A reporter returns any time, enters their token, and sees the current status (received, under review, more information requested, resolved) along with any note the safeguarding officer has left for them — without ever learning who is handling the case.

### Reporting without internet
The "No internet?" tab is a working simulation of a USSD flow — dial `*123#` and navigate a real menu by typing numbers, the way it would work on a basic phone with no data connection. Reports made this way land in the same system as reports made through the web form.

### Staff dashboard
A designated safeguarding officer logs in (demo passphrase: `safeguard2026` — for demonstration only, not real security) to see incoming reports filtered by centre, update their status, and leave a note the reporter can see. This is what closes the "reports go nowhere" trust gap.

## Real-world conditions this design considers

- **Trust & anonymity** — no identity required to report; identity is opt-in, never assumed
- **Low bandwidth** — a working offline/USSD-style path alongside the web form
- **Accessibility** — short categorical choices instead of relying on free text, larger touch targets, high contrast
- **Multilingual access** — English, Hausa, Yoruba, and Igbo included as a demonstration of intent, not full coverage
- **Local relevance** — reports route by named exam centre, so escalation can stay local

## What's simulated vs. real in this proof of concept

This is a hackathon PoC, not a production system. A few things are deliberately simplified:

| In this demo | In a real deployment |
|---|---|
| Reports are stored in the browser's local storage | A real backend and database |
| USSD flow is simulated in-browser | Integration with an actual telecom USSD gateway |
| Staff login is a shared passphrase | Proper authentication and role-based access |
| Four languages, partial coverage | Full localization reviewed by native speakers |

## Running it

No build step or dependencies. Open `safereport.html` directly in a browser, or serve the repo with GitHub Pages.

## Why it's worth developing further

Exam centres are a controlled, recurring, high-stakes environment — a strong place to pilot a safeguarding channel before extending it to other public-facing programs. The core reporting and triage model (anonymous token, opt-in contact, dual online/offline access, officer-visible-but-identity-protected notes) generalizes well beyond exams to any event context named in the brief.
