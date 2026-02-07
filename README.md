# QSP Stage180 — SDK Entry Point (v2.0 Preview)

![CI](https://github.com/mokkunsuzuki-code/stage180/actions/workflows/stage180-ci.yml/badge.svg)

> **Attack-driven SDK entry point.**  
> Security regressions are automatically detected by CI.

---

## What this is
QSP Stage180 provides a **minimal SDK entry point** that external developers
and researchers can integrate directly into their applications.

Security properties are not just documented — they are **enforced by
reproducible attack runners executed in CI**.

---

## Quick start (10 minutes)

### Install
```bash
pip install -e .
Run server (10 lines)
python examples/hello_10lines_server.py
Run client (10 lines)
python examples/hello_10lines_client.py
Expected output (example):

[client] started session_id=... epoch=1 mode=QKD_MIXED
[client] recv: pong
[client] receipt: session_id=... chain=...
What CI guarantees
This repository is protected by attack-driven CI.

Each push automatically verifies:

Normal communication succeeds

Tampered frames are deterministically rejected

Security regressions are blocked before merge

See docs/STAGE180_CLAIMS.md for CI-bound security claims.

Security scope
Guaranteed
Session binding (wrong session_id is rejected)

Fail-closed behavior on tampering

Deterministic rejection path

Non-goals
Replay resistance

Side-channel resistance

Hardware QKD behavior

Performance benchmarking

Non-goals are explicitly documented to keep reviews precise.

Attack coverage (CI-enforced)
Attack scenario	Status	CI
Wrong Session ID	Prevented	✅
Replay attack	Planned	⏳
Epoch rollback	Planned	⏳
Algorithm downgrade	Planned	⏳
Repository structure
.
├── qsp/                    # SDK entry point
├── examples/               # 10-line demos
├── attack_scenarios/       # Reproducible attacks
├── docs/                   # Security claims
├── .github/workflows/      # CI enforcement
├── README.md
└── pyproject.toml
Why Stage180 matters
Stage170–179 focused on correctness and rigor.
Stage180 shifts the value source to usability and enforcement.

Security claims become executable.
Reviews become hands-on.
Breakage becomes immediately visible.

License
MIT License © 2025 Motohiro Suzuki