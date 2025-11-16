## **MILESTONE 2 PLAN: OpenArkiv**

**Team:** OpenArkiv
**Track:** [✓] SHIP-A-TON [ ] IDEA-TON
**Date:** 16-11-2025

---

## 📍 WHERE WE ARE NOW

**What we built/validated this weekend:**

* Designed full OpenArkiv architecture (Mesh → cMixx → Beacon → Arkiv DB-chain).
* Implemented initial BLE mesh broadcast & relay prototype.
* Integrated xxDK/cMixx messaging for Whistleblower Mode experimental flow.
* Created Beacon server logic (signature recovery → Arkiv submission).
* Defined Arkiv DB-chain schema for payload + metadata storage.

**What's working:**

* Payload creation + authentication on client.
* BLE device discovery and multi-hop forwarding.
* cMixx payload wrapping and anonymized transmission (early path test).
* Beacon receiving and validating signed messages.

**What still needs work:**

* Stable BLE store-and-forward under movement and sleep conditions.
* Full message chunking/reassembly for larger media.
* Anonymous → Beacon → Arkiv flow reliability improvements.
* Production-ready Arkiv submission with retries/fallbacks.

**Blockers or hurdles we hit:**

* BLE bandwidth limitations requiring chunk-level optimization.
* cMixx documentation gaps around batching and exit-node routing.
* Beacon discovery edge cases where nodes intermittently lose internet.
* Arkiv SDK inconsistencies between devnet vs local testnet.

---

## 🚀 WHAT WE'LL SHIP IN 30 DAYS

**Our MVP will do this:**
OpenArkiv will allow anyone to create an encrypted payload, send it across a local Bluetooth mesh without internet, and have a Beacon device upload it to Arkiv. Users can choose between signed journalist mode or fully anonymous whistleblower mode using cMixx.

---

### **Features We'll Build (3–5 max)**

---

### **Week 1–2**

**Feature:** Reliable Mesh Messaging v1
**Why it matters:** The mesh is the foundation; data must travel hop-by-hop without internet.
**Who builds it:** ___________

**Feature:** Passkey → Wallet Derivation + Signed Mode
**Why it matters:** Enables verifiable journalist submissions with provenance.
**Who builds it:** ___________

---

### **Week 2–3**

**Feature:** cMixx Whistleblower Mode Integration
**Why it matters:** Ensures metadata-free submissions for high-risk users; core differentiator.
**Who builds it:** ___________

**Feature:** Beacon Node + Arkiv Submission
**Why it matters:** Beacon is the exit point to Arkiv; must be stable and reliable.
**Who builds it:** ___________

---

### **Week 3–4**

**Feature:** Payload Chunking + Reassembly
**Why it matters:** Enables photo/video evidence to be sent reliably through BLE mesh & cMixx.
**Who builds it:** ___________

**Feature:** Arkiv Dashboard (simple viewer)
**Why it matters:** Lets judges and users see live submissions coming from the mesh.
**Who builds it:** ___________

---

### **Team Breakdown**

**Fabian Ferno – Backend

* Owns: Beacon logic, signature recovery, Arkiv integration.

* Owns: UI, passkey wallets, cMixx integration, payload creation.

* Owns: DB-chain schema, indexers, dashboard. 

** Romario Kavin – Mesh Networking Lead** | [X hrs/week

* Owns: BLE multi-hop, store-and-forward, chunking.

---

## 🧭 MENTORING & EXPERTISE WE NEED

**Areas where we need support:**

* BLE mesh stability in high-device-density environments.
* Optimizing cMixx routing paths + batching.
* Designing reliable Arkiv DB-chain indexing models.

**Specific expertise we're looking for:**

* Someone who has built decentralized mesh apps (Briar, Bridgefy, BitChat).
* Expert in mixnets, metadata protection, or xxDK internals.
* Arkiv SDK contributor for performance tuning + schema guidance.

---

## 🎯 WHAT HAPPENS AFTER

**When M2 is done, we plan to...**

* Deploy OpenArkiv in a real world stress test (crowded public area).
* Begin external testing with journalists/human rights groups for feedback.
* Package a downloadable early MVP mobile app.

**And 6 months out we see our project achieve:**

* Full-featured resilient mesh + anonymous routing stack.
* NGO and investigative journalist partners using OpenArkiv in real scenarios.
* A public Arkiv-backed database of verified global submissions.
* Establish OpenArkiv as the default censorship-proof submission tool for high-risk regions.
