# Security Policy

We take the security of AnthraCode and its users seriously. AnthraCode is an
autonomous agent that can read, write, and execute code on a user's machine, so
we treat security reports with priority.

## Supported versions

Security fixes are provided for the **latest** published release of
`anthracode-ai` on npm. Please upgrade before reporting:

```bash
npm install -g anthracode-ai@latest
```

## Reporting a vulnerability

**Please do not open a public issue for security vulnerabilities.**

Report privately through either channel:

1. **GitHub private vulnerability reporting** — open a draft advisory at
   the repository's *Security → Report a vulnerability* tab (preferred).
2. **Email** — **security@anthracode.com** with:
   - a description of the vulnerability and its impact,
   - steps to reproduce (proof-of-concept if possible),
   - affected version(s) and platform,
   - any suggested remediation.

## What to expect

| Stage | Target |
|-------|--------|
| Acknowledgement of your report | within **3 business days** |
| Initial assessment / severity | within **7 business days** |
| Fix or mitigation plan | communicated after assessment |
| Public disclosure | coordinated with you after a fix ships |

We follow **coordinated disclosure**: we ask that you give us a reasonable
window to release a fix before any public disclosure, and we will credit you in
the release notes unless you prefer to remain anonymous.

## Scope

In scope:
- the `anthracode-ai` client and its published binaries,
- the platform packages (`anthracode-windows-x64`, `anthracode-linux-x64`),
- the install/postinstall flow.

Out of scope (report to the respective owner):
- third-party AI providers and their APIs,
- upstream OpenCode infrastructure (zen gateway, share service),
- vulnerabilities in third-party dependencies (please still tell us so we can
  upgrade).

## Safe harbor

We will not pursue legal action against researchers who:
- act in good faith,
- avoid privacy violations, data destruction, and service disruption,
- do not access or modify data beyond what is necessary to demonstrate the
  issue, and
- give us a reasonable time to respond before public disclosure.

Thank you for helping keep AnthraCode and its users safe.
