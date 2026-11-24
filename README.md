# Awesome Vibe-Code & AI Web App Security [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated, practical list of security tools, checklists, templates, hardening guides, and research for web apps built fast with **Cursor, Lovable, Bolt, v0, Replit, Next.js, Supabase, Postgres, Stripe, and LLM APIs**.

Maintained by **[Shipmate](https://shipmate.agency)**. PRs adding genuinely useful, open, vendor-neutral security resources are welcome (see [CONTRIBUTING.md](./CONTRIBUTING.md)).

## Contents
- [Pre-Launch Scanners & MCP Tools](#pre-launch-scanners--mcp-tools)
- [IDE Guardrails (Cursor, Claude Code, Copilot)](#ide-guardrails-cursor-claude-code-copilot)
- [Supabase & Postgres RLS Hardening](#supabase--postgres-rls-hardening)
- [Next.js, Vercel & React Security](#nextjs-vercel--react-security)
- [Stripe & Billing Webhook Security](#stripe--billing-webhook-security)
- [AI / LLM Endpoint & Prompt Security](#ai--llm-endpoint--prompt-security)
- [Enterprise Reviews, SOC 2 & Attestation Templates](#enterprise-reviews-soc-2--attestation-templates)
- [Secrets, Dependencies & Headers](#secrets-dependencies--headers)
- [Benchmarks & Public Security Standards](#benchmarks--public-security-standards)

---

## Pre-Launch Scanners & MCP Tools
- [ShipReady](https://github.com/Shipmate-agency/shipready) — Zero-dependency CLI & GitHub Action checking Supabase RLS, exposed secrets, Stripe webhooks, and headers.
- [ShipReady MCP](https://github.com/Shipmate-agency/shipready-mcp) — Local stdio MCP server bringing pre-launch security checks into Cursor, Claude Code, and Windsurf.
- [Semgrep](https://github.com/semgrep/semgrep) — Fast static analysis with strong JS/TS/React/Python security rulesets.
- [Gitleaks](https://github.com/gitleaks/gitleaks) — Secret scanner for Git repos, pre-commit hooks, and CI pipelines.
- [TruffleHog](https://github.com/trufflesecurity/trufflehog) — Finds and verifies live leaked credentials across repos and history.
- [Trivy](https://github.com/aquasecurity/trivy) — Vulnerability, IaC, and secret scanner for containers, lockfiles, and repositories.
- [Nuclei](https://github.com/projectdiscovery/nuclei) — Template-based vulnerability scanner for authorized staging/production testing.
- [OWASP ZAP](https://github.com/zaproxy/zaproxy) — Open-source web application dynamic security scanner (DAST).

## IDE Guardrails (Cursor, Claude Code, Copilot)
- [ShipReady `.cursorrules` & `CLAUDE.security.md`](https://github.com/Shipmate-agency/shipready-mcp) — Drop-in security invariants enforcing RLS, verified Stripe webhooks, Server Action auth, and AI token caps.
- [awesome-cursorrules](https://github.com/PatrickJS/awesome-cursorrules) — Community directory of `.cursorrules` files across frameworks.
- [OWASP Secure Coding Practices Quick Reference](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/) — Language-agnostic secure defaults checklist.

## Supabase & Postgres RLS Hardening
- [Supabase Row Level Security Docs](https://supabase.com/docs/guides/database/postgres/row-level-security) — Official Postgres RLS guide and policy patterns.
- [Supabase Database Linter](https://supabase.com/docs/guides/database/database-linter) — Built-in linter catching `rls_disabled_in_public` and `security_definer_view`.
- [Supabase RLS Audit Pack](https://github.com/Shipmate-agency/supabase-rls-audit-pack) — Single read-only SQL query listing public tables missing RLS, `USING (true)` write policies, and `SECURITY DEFINER` views.
- [Two-Account Supabase RLS Isolation Test](https://shipmate.agency/articles/supabase-rls-two-account-test) — How to verify tenant boundaries using two separate logins instead of trusting static checks.
- [Fix `rls_disabled_in_public` & `security_definer_view`](https://shipmate.agency/articles/supabase-rls-disabled-in-public-fix) — Exact Postgres 15+ SQL fixes.
- [Supabase Anon Key vs Service Role Key](https://shipmate.agency/articles/supabase-anon-key-vs-service-role-key) — What belongs in the browser and what never should.

## Next.js, Vercel & React Security
- [Next.js Data Security Guide](https://nextjs.org/docs/app/guides/data-security) — Official Next.js guidance on Data Access Layers, Server Actions, and taint APIs.
- [Next.js Server Actions Are Public Endpoints](https://shipmate.agency/articles/nextjs-server-actions-are-public-endpoints) — Why every `"use server"` function needs explicit session and ownership checks.
- [Vercel Firewall & Rate Limiting](https://vercel.com/docs/vercel-firewall) — Edge WAF and per-IP/route rate limits for Next.js apps.
- [Cloudflare WAF & Turnstile](https://developers.cloudflare.com/turnstile/) — Bot protection and edge rules without heavy CAPTCHAs.

## Stripe & Billing Webhook Security
- [Stripe Webhook Signature Verification Docs](https://docs.stripe.com/webhooks/signature) — Official HMAC verification guide.
- [Verified Next.js App Router Stripe Webhook Handler](https://github.com/Shipmate-agency/stripe-webhook-audit-nextjs) — Copy-paste `route.ts` fixing `No signatures found matching the expected signature for payload` without disabling verification.
- [Stripe Secret Keys in `NEXT_PUBLIC_` Variables](https://shipmate.agency/articles/stripe-secret-key-in-client-javascript-next-public) — How client env prefixes leak server secrets into browser bundles.

## AI / LLM Endpoint & Prompt Security
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) — Prompt injection, sensitive info disclosure, unbounded consumption (Denial of Wallet), and excessive agency.
- [Stop a Runaway AI API Bill](https://shipmate.agency/articles/stop-runaway-ai-bill) — Auth, rate limits, `max_output_tokens`, and hard spend caps for OpenAI/Anthropic routes.
- [Upstash Ratelimit](https://github.com/upstash/ratelimit-js) — Serverless HTTP rate limiting for Next.js / Edge API routes.
- [MCP Security Best Practices](https://modelcontextprotocol.io/specification/draft/basic/security_best_practices) — Official security considerations for Model Context Protocol servers and clients.

## Enterprise Reviews, SOC 2 & Attestation Templates
- [Pentest Attestation Letter Template](https://github.com/Shipmate-agency/pentest-attestation-letter-template) — Clean Markdown template showing what goes into a buyer-ready pentest letter ([live sample](https://shipmate.agency/sample-letter)).
- [Startup Security Questionnaire Answers (SIG Lite / VSA)](https://github.com/Shipmate-agency/startup-security-questionnaire-answers) — Honest starter answers to 18 common enterprise vendor review questions.
- [Does SOC 2 Require a Pentest?](https://shipmate.agency/articles/does-soc-2-require-a-pentest) — What AICPA Trust Services Criteria actually ask for.
- [Google OAuth CASA Tier 2 Assessment Guide](https://appdefensealliance.dev/casa) — Official App Defense Alliance CASA requirements (plus [pre-flight checklist](https://shipmate.agency/articles/google-oauth-casa-tier-2-preflight)).
- [Cloud Security Alliance CAIQ](https://cloudsecurityalliance.org/research/cloud-controls-matrix) — Standard cloud security questionnaire framework.

## Secrets, Dependencies & Headers
- [MDN HTTP Observatory](https://developer.mozilla.org/en-US/observatory) — Public HTTP security header and TLS analyzer.
- [Shipmate Security Header Checker](https://shipmate.agency/tools/security-headers) — Checks 6 key headers with copy-paste fixes for Vercel, Netlify, Next.js, and Cloudflare.
- [OSV-Scanner](https://github.com/google/osv-scanner) — Google's open-source dependency vulnerability scanner backed by OSV.dev.
- [Socket.dev](https://socket.dev/) — Supply-chain security analysis for npm and PyPI packages.

## Benchmarks & Public Security Standards
- [Vibe-Vuln-Bench](https://github.com/Shipmate-agency/vibe-vuln-bench) — Standardized SaaS prompt and 10-check security grader for comparing AI app builders.
- [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/) — Application Security Verification Standard (baseline used by CASA Tier 2 and manual web pentests).
- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/) — Concise, battle-tested reference sheets for auth, sessions, CSRF, CSP, and SQLi.

---

## Contributing
Have an open-source tool, real hardening guide, or framework security checklist? Open a PR following [CONTRIBUTING.md](./CONTRIBUTING.md).
