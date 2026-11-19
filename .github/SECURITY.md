# Security Policy

## Reporting a Vulnerability

The Stirling-PDF team takes security vulnerabilities seriously. We appreciate your efforts to responsibly disclose your findings.

### How to Report

You can report security vulnerabilities through two channels:

1. **GitHub Security Advisory**:
   - Navigate to the [Security tab](https://github.com/Stirling-Tools/Stirling-PDF/security) in our repository
   - Click on "Report a vulnerability"
   - Provide a detailed description of the vulnerability

2. **Direct Email**:
   - Send your report to security@stirlingpdf.com
   - Please include as much information as possible about the vulnerability

### What to Include

When reporting a vulnerability, please provide:

- A clear description of the vulnerability
- Steps to reproduce the issue
- Any potential impact
- If possible, suggestions for addressing the vulnerability
- Your contact information for follow-up questions

### Response Time

We are currently receiving a high volume of security reports, many of them AI-assisted, and each one is reviewed by hand. Because of this, acknowledging a report can take 1-2 weeks or longer. Critical issues are prioritised.

Reports that include a working proof of concept against the latest version are triaged first. Reports we cannot reproduce may be closed without further investigation.

### Process

1. Submit your report through one of the channels above
2. Receive an acknowledgment from our team
3. Our team will investigate and validate the issue
4. We will work on a fix and keep you updated on our progress
5. Once resolved, we will publish the fix and acknowledge your contribution (if desired)

### Bug Bounty

At this time, we do not offer a bug bounty program. However, we greatly appreciate your efforts in making Stirling-PDF more secure and will acknowledge your contribution in our release notes (unless you prefer to remain anonymous).

## Supported Versions

Only the latest version of Stirling-PDF is supported for security updates. We do not backport security fixes to older versions.

| Version | Supported          |
| ------- | ------------------ |
| Latest  | :white_check_mark: |
| Older   | :x:               |

**Please note:** Before reporting a security issue, ensure you are using the latest version of Stirling-PDF. Security reports for older versions will not be accepted.

## Security Best Practices

When deploying Stirling-PDF:

1. Always use the latest version
2. Follow our deployment guidelines
3. Regularly check for and apply updates

## Documented residual risks (no fixed release reachable in this tree)

Verified 2026-11-19 against the crates.io / npm registry dependency APIs.
None of these are dismissed or muted; each is blocked by an upstream
release that does not exist yet.

### `extract-zip` 2.0.1 (2 Dependabot alerts; advisory covers <= 2.0.1)
- Chain: `@puppeteer/browsers` -> `extract-zip ^2.0.1`. `2.0.1` is the
  NEWEST published release (`npm view extract-zip dist-tags.latest`), and
  the advisory has no patched version. Reached only when Puppeteer
  downloads a browser during development; unfixable until upstream
  publishes a fix.

### `glib` 0.18.5 (1 Dependabot alert; fix 0.20.0)
- Chain: `tauri 2.12.7` (latest stable) -> `gtk ^0.18` -> `glib ^0.18`.
  The `gtk` crate's newest release (0.19.0) requires `glib ^0.22`, and no
  tauri release accepts gtk 0.19+, so `glib >= 0.20` is unreachable from
  any tauri-based tree today. Linux-desktop-only dependency.
