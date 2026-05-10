**CleanRepairLite** is a premium, commercial-grade Supervised Fine-Tuning (SFT) dataset designed to train the next generation of AI coding agents, DevSecOps Copilots, and auto-remediation tools.

Stop training your security models on noisy, hallucinated GitHub scrapes. We provide **100% verified, real-world before/after code repairs** extracted directly from production repositories and official PyPI version diffs.

## 🚀 Why CleanRepairLite?

* **Strict Ground Truth:** No LLM-generated fixes. Every fixed code snippet is a real commit or official package version fix.
* **100% Sanitized:** Passed through rigorous pipeline. Zero leaked AWS keys, passwords, or PII. Compliance-ready.
* **Commercial-Safe Licenses:** Contains only permissive licenses (MIT, Apache-2.0, BSD, ISC). Zero GPL contamination.
* **Deterministic Taxonomy (v0.3):** Mapped to CWEs, Exploitability, and Attack Scenarios without "Raw Chain-of-Thought" hallucinations.

## 🔍 The Schema (What's Inside)

Each JSONL record represents a strictly validated vulnerability fix pair. Here is a simplified view of our unique `vulnerability_explanation` layer:

```json
"vulnerability_explanation": {
  "cwe": ["CWE-94"],
  "cwe_name": "Improper Control of Generation of Code ('Code Injection')",
  "vulnerable_behavior": "The application evaluates untrusted Python code in an unrestricted namespace, allowing arbitrary code execution (RCE).",
  "fix_mechanism": "Restricted the evaluation namespace by setting '__builtins__' to an empty dictionary.",
  "patch_difficulty": "Medium",
  "grounding": {
    "diff_grounded": true
  }
}
