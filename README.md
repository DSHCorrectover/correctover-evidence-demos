# Correctover Evidence Demos

Hash-anchored, Ed25519-signed evidence bundles. Every bundle: RFC 8785 JCS canonical record → SHA-256 → Ed25519 signature. Re-derive and re-verify without trusting us.

| Bundle | Class | Digest (record) |
|---|---|---|
| [weak-entropy-recovery-demo-20261028.json](weak-entropy-recovery-demo-20261028.json) | low-entropy secp256k1 key recovery, end-to-end | see receipt in bundle |

Verification: canonicalize the `record` field with RFC 8785 (purified number semantics), SHA-256 it, compare to receipt.digest_sha256; verify receipt.ed25519_signature over the canonical bytes with receipt.ed25519_public_key_demo.
