
## **MILESTONE 2 PLAN: OpenArkiv**

**Team:** OpenArkiv
**Track:** [✓] SHIP-A-TON [ ] IDEA-TON  
**Date:**  20-11-2025

---

## 📍 WHERE WE ARE NOW

**What we built/validated this weekend:**
- Designed full end-to-end architecture: Mesh → cMixx → Beacon → Arkiv DB-chain.
- Built initial BLE mesh prototype for offline packet broadcast and relaying.
- Integrated xxDK/cMixx for early Whistleblower Mode anonymized message transport.
- Implemented Beacon logic to receive payloads and submit to Arkiv testnet.
    
**What's working:**
- Client can create and sign  text payloads (text).
- BLE multi-hop relays function across multple devices.
- Basic cMixx payload routing to exit node → Beacon. (slow initialization due to gateways)

**What still needs work:**
- Stable chunking + reassembly for larger payloads (photos/videos).
- Reliable Beacon → Arkiv submission with retries and fallback logic.
- Upload other file type payloads through the network
- Location based queries for the submitted payloads across a the "OpenArk" map view
    
**Blockers or hurdles we hit:*
- BLE bandwidth & connection reliability under movement.
- cMixx documentation gaps around batching and delivery guarantees.
- cmixx xxdk SDK go lang to typescript connectors -adapters
    
---

## 🚀 WHAT WE'LL SHIP IN 30 DAYS

**Our MVP will do this:**  
OpenArkiv will let a user create an encrypted payload (text + file upload), send it across a Bluetooth mesh with zero internet, and have a Beacon device upload it to Arkiv. Users can choose between Verified (signed) mode and Anonymous (cMixx) mode, ensuring safe, censorship-resistant reporting for journalists and whistleblowers.

---

### **Features We'll Build (3–5 max)**

---

**Week 1–2:**

- **Feature:** Mesh Messaging v1: Reliable BLE multi-hop with store-and-forward (multi device hops need to implemented at scale)- prevent fails and add basic queue logic for message relays.
- **Why it matters:** This is the foundation — without reliable mesh, no offline transmission is possible.
- **Who builds it:** Romario Kavin
    

---

**Week 2–3:**

- **Feature:** Signed Mode (Passkey → Wallet Derivation + Signature Validation)
- **Why it matters:** Enables provenance-backed journalism and verified submissions.
- **Who builds it:** Romario Kavin
- **Feature:** Whistleblower Mode using cMixx (xxDK Integration).
- **Why it matters:** Provides metadata-free anonymity for high-risk users.
- **Who builds it:** Fabian Ferno
    

---

**Week 3–4:**

- **Feature:** Beacon Node v1: Payload receive → verify signatue + decrypt → submit to Arkiv
- **Why it matters:** This is the bridge from offline → on-chain, completing the entire flow.
- **Who builds it:**  Fabian Ferno
- **Feature:** Payload Chunking + Reassembly
- **Why it matters:** Allows sending actual photos/videos over BLE and cMixx reliably.
- **Who builds it:** Romario Kavin
    

---

### **Team Breakdown (if applicable)**

**[[Fabian Ferno]] – Protocol Design, Backend, PM** | [X hrs/week]
- Owns: BLE protocol architecture, Arkiv submission logic, indexing, cMixx integration, xxDK flows, Beacon coordination server, project management
    
**[[Romario Kavin]] – Swift iOS Dev, Product** | [X hrs/week]
- Owns: BLE, mesh implementation, Payload creation, passkey wallets, UI, signed mode, multi-hop logic, chunking, Beacon node implementation

---

### **Mentoring & Expertise We Need**

**Areas where we need support:**
- BLE multi-hop reliability + performance tuning.
- Best practices for cMixx batching and exit-node routing.
    

**Specific expertise we're looking for:**
- Mixnets, xxDK integrations, metadata protection.
- Arkiv DB-chain design and indexing strategies.
- Mobile OS constraints around BLE & background execution.

---

## 🎯 WHAT HAPPENS AFTER

**When M2 is done, we plan to…**

- Conduct a real-world stress test (campus/protest simulation).
- Release the first downloadable MVP to early journalist/NGO testers.
    

**And 6 months out we see our project achieve:**

- We will launch the app on the ios app store
- The default mobile tool for censorship-resistant reporting during internet blackouts.
- Partnerships with human rights orgs, journalist networks, and DePIN field data programs.
    
---
