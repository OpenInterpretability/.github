# Security Policy

## Reporting a vulnerability

**Do not open a public issue.** Instead, email **hi@openinterp.org** with:

- A short description of the problem.
- Steps to reproduce (or a small repro repo).
- Your assessment of severity (low / medium / high) and why.
- Whether you need a public CVE.

We will acknowledge within **72 hours** and aim to land a fix within **14 days** for high-severity issues.

## Scope

### In scope
- Remote code execution or arbitrary file write via the `openinterp` Python package, mechreward library, or any notebook on `OpenInterpretability/notebooks`.
- Authentication / data-exposure issues on openinterp.org.
- Prompt-injection or model-card poisoning that affects rendering on openinterp.org.
- Dependency supply-chain issues affecting our published wheels.

### Out of scope
- Issues with third-party HuggingFace models we reference but do not host.
- Denial of service via resource exhaustion on user's own Colab runtime.
- Cosmetic bugs or non-exploitable crashes.

## Coordinated disclosure

We follow a **90-day** embargo by default for non-trivial issues. After fix + release we publish a note in the repo's `SECURITY.md` or a `CVE-XXXX-XXXX` entry.

## Safe-harbor

Good-faith security research — including accessing your own account, staying within scope, and not exfiltrating others' data — is welcome. We will not pursue legal action.

---

Thanks for helping make OpenInterpretability safer. If you save the field a headache, we will credit you publicly (with your permission).
