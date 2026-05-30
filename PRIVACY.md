# AnthraCode — Privacy Policy

**Last updated: 2026-05-30**

AnthraCode is a **local-first** command-line tool. It runs on your machine and
operates on your local files. We (the AnthraCode project) **do not operate a
backend that collects your code, prompts, or usage**, and AnthraCode contains
**no third-party analytics or tracking SDKs** (no Google Analytics, Segment,
PostHog, Sentry, Amplitude, Mixpanel, or similar).

This policy explains every situation in which data leaves your machine. It is
based on an audit of the source code, not generic boilerplate.

**Data controller:** Silo Khalaf, *entrepreneur individuel* (RAFA57), 6 Faubourg
Sainte-Croix, 57600 Forbach, France — **privacy@anthracode.com** (see
`LEGAL_NOTICE.md`).

---

## 1. What stays on your machine

By default, the following never leave your computer:

- your source code and files,
- your prompts and AnthraCode's responses,
- your configuration and credentials,
- your session history (stored in a local database).

## 2. What leaves your machine, and when

AnthraCode connects to external services only in the situations below.

### 2.1 AI provider requests — required for the core function
When you send a message, AnthraCode transmits your prompt and the relevant file
context to **the AI provider you configured** (e.g. Anthropic, OpenAI, Google,
Groq, Ollama, or any OpenAI-compatible endpoint), using **your** API key. We are
not a party to this exchange. The provider's privacy policy and terms govern that
data. AnthraCode does not route these requests through our servers.

### 2.2 Free "zen" model gateway — only if you use it
If you use the bundled free `opencode` provider (no API key, no login),
AnthraCode sends those requests to the OpenCode zen gateway
(`https://opencode.ai/zen/v1`), operated by the upstream OpenCode project, under
their terms. This applies **only** when you select that provider.

### 2.3 Update check — on by default, opt-out
On launch (throttled by a local cache) AnthraCode checks the npm registry and
GitHub for a newer version. Disable with `ANTHRACODE_DISABLE_AUTOUPDATE=true`.

### 2.4 Model catalog — on by default, opt-out
AnthraCode fetches the public model catalog from `models.dev` to list available
models. Disable with `ANTHRACODE_DISABLE_MODELS_FETCH=true`.

### 2.5 Language-server downloads — on by default, opt-out
On first use of a language feature, AnthraCode may download language servers from
their official sources (GitHub, JetBrains, HashiCorp CDNs). Disable with
`ANTHRACODE_DISABLE_LSP_DOWNLOAD=true`.

### 2.6 Skills hub — on demand only
When you search for or install a skill, AnthraCode queries `skills.sh`. This
happens only when you initiate it.

### 2.7 ChatGPT / Codex usage check — only with ChatGPT auth, opt-out
When authenticated to ChatGPT/Codex, AnthraCode makes a best-effort call to the
ChatGPT usage endpoint to show your remaining quota. Disable with
`ANTHRACODE_CODEX_USAGE=false`.

### 2.8 Session sharing — OFF by default, opt-in
AnthraCode can share a session via a link. This is **disabled by default** and
only uploads when you explicitly share (or set `ANTHRACODE_AUTO_SHARE=true`).
Shared content goes to the OpenCode share service.

### 2.9 Telemetry (OpenTelemetry) — OFF by default, opt-in
AnthraCode emits traces **only if you set** `OTEL_EXPORTER_OTLP_ENDPOINT`. The
data goes to **your** collector — never to us. With no endpoint set, no telemetry
is produced.

### 2.10 Web fetch / web search tools — on demand only
If the agent uses the `webfetch` or `websearch` tools, it contacts the URLs or
search provider required for that specific request.

## 3. We do not sell or share your data

We do not have your data to sell. AnthraCode does not transmit your code,
prompts, or usage to AnthraCode-operated servers.

## 4. Children's privacy

AnthraCode is a developer tool not directed to children under 13 (or the
applicable age in your jurisdiction).

## 5. Your controls

- Choose your AI provider (where your prompts go).
- Disable update checks, model fetch, LSP downloads, the usage probe, and sharing
  via the environment flags listed above (see `FLAGS.md` in the source repo).
- Telemetry is off unless you opt in.

## 6. Your rights (GDPR / EU)

Because AnthraCode is local-first, we (the publisher) do not hold a central store
of your personal data — your prompts, code, and history stay on your device, and
we operate no analytics backend. Where the EU General Data Protection Regulation
(GDPR) applies, you have the rights of access, rectification, erasure,
restriction, portability, and objection regarding any personal data we would
process. Since we hold essentially none, most requests are satisfied locally by
you (deleting your local data) or by the third-party provider you chose (for data
you sent them).

To exercise a right against us, contact **privacy@anthracode.com**. If you
believe we have mishandled your data, you may lodge a complaint with the French
data-protection authority, the **CNIL** (https://www.cnil.fr), or your local EU
supervisory authority.

## 7. Changes

Material changes are reflected by the "Last updated" date and published here.

## 8. Contact

Privacy questions / data controller: **privacy@anthracode.com**
Silo Khalaf (RAFA57), Forbach, France — see `LEGAL_NOTICE.md`.

> This document describes the behavior of the open-source AnthraCode client. It
> is provided for transparency and does not, by itself, constitute legal advice.
