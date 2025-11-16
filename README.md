# **OpenArkiv — README**

```markdown
# OpenArkiv  
A censorship-resistant, offline-first data submission protocol for journalists, whistleblowers, and citizens in high-risk environments.

OpenArkiv enables encrypted messages to travel across phones using Bluetooth mesh networking until they reach a device with internet access, which submits the data to the Arkiv Network for permanent, verifiable storage. Users can choose between identity-backed submissions or fully anonymous whistleblower mode.

---

## 🚨 Why OpenArkiv?

Around the world, governments shut down the internet during protests, elections, and crises.  
This prevents:
- Journalists from transmitting evidence  
- Citizens from reporting abuses  
- Whistleblowers from leaking information safely  

**OpenArkiv ensures that truth can still flow — even when the internet doesn’t.**  
It creates a resilient pipeline that works in total blackout environments.

---

## 🧠 Core Concept

OpenArkiv combines:
1. **Offline Bluetooth Mesh Networking** (inspired by Jack Dorsey’s BitChat)  
2. **Anonymous, metadata-protected messaging** via **xxDK**  
3. **Tamper-proof, verifiable on-chain storage** using the **Arkiv Network**

The system moves data from:
**User → Nearby Devices (BLE) → Beacon → Arkiv DB-Chain**

No servers.  
No SIM cards.  
No internet required until the final step.

---

## 🏛 Architecture Overview

```

User Device
├── Create Payload (text/photo/video)
├── Choose Mode: Signed / Whistleblower
├── Encrypt or Sign Payload
└── Broadcast via Bluetooth

OpenArkiv Mesh (Offline)
├── Device-to-device Bluetooth hops
├── Store-and-forward relaying
└── Opportunistic delivery to any Beacon device

Beacon Device (Has Internet)
├── Reassembles relayed packets
├── Validates signature (if signed mode)
├── Derives deterministic server wallet from recovered address
└── Submits payload to Arkiv Network

Arkiv Network (On-chain Storage)
├── Stores payload on DB-chain
├── Ensures immutability, verifiability, and global availability
└── Provides queryable endpoints and proofs

````

---

## 🔐 Modes of Operation

### **1. Signed Mode (Journalists & Verified Submitters)**  
- Device generates a wallet from the passkey (FaceID/TouchID).  
- Payload is signed using this local private key.  
- GPS coordinates & timestamp optionally included.  
- Beacon recovers signer → derives a server-side wallet → submits to Arkiv.

**Use case:** Verified citizen journalism, attribution-required reporting.

---

### **2. Whistleblower Mode (Anonymous & Metadata-Protected)**  
Powered by the **xxDK**:  
- End-to-end encryption  
- Metadata stripping (no IP, no device identifiers)  
- Resistant to traffic analysis  
- No signatures or GPS metadata  

**Use case:** High-risk reporters, anonymous leaks, dissident communication.

---

## 📡 Data Flow Diagram (Mermaid)

```mermaid
flowchart LR
    subgraph UserDevice["User Device"]
        A[Create Payload]
        B[Select Mode]
        C[Encrypt/Sign Payload]
    end

    subgraph Mesh["OpenArkiv BLE Mesh"]
        D[Device → Device<br/>Bluetooth Hops]
    end

    subgraph Beacon["Beacon Node (Online)"]
        E[Receive Payload]
        F[Verify or Decrypt]
        G[Submit to Arkiv]
    end

    subgraph Arkiv["Arkiv Network"]
        H[DB-Chain Storage]
        I[Permanent, Verifiable Record]
    end

    A --> B --> C --> D --> E --> F --> G --> H --> I
````

---

## 🧩 Components

### **openarkiv-mesh**

Fork of BitChat’s mesh protocol with:

* BLE advertising & scanning
* Store-and-forward packet relay
* Multi-hop routing logic
* Packet encryption

### **openarkiv-client**

Mobile client responsible for:

* Payload creation
* Selecting signed/anonymous mode
* Integrating xxDK for whistleblower submissions
* Using passkeys to generate local wallets

### **openarkiv-beacon**

A device or server that:

* Listens for incoming mesh packets
* Has intermittent internet access
* Validates or decrypts messages
* Submits to Arkiv DB-chains
* Returns submission receipts

### **arkiv-dataset**

Schema & CRUD logic for storing:

* Payload
* Metadata (or intentionally none in anonymous mode)
* Submission timestamp
* Optional GPS & signature info
* Proofs of inclusion

---

## 📦 Installation & Setup (Coming Soon)

We are preparing:

* Docker setup
* Mobile dev quickstart
* Beacon node deployment guide
* Arkiv DB-chain initialization scripts

If you're testing the prototype, reach out or check the `dev` branch for instructions.

---

## 🧪 Use Cases

* Censorship-resistant journalism
* Whistleblower leaks
* Evidence submission during protests
* Disaster communication (no internet)
* Secure reporting for NGOs and human rights orgs
* DePIN field data harvesting in offline zones

---

## 🌍 Why Arkiv?

Arkiv provides:

* Deterministic, decentralized database layer
* Rich queries + CRUD
* Programmable expiry
* GLM-based gas model
* Fully transparent and tamper-proof storage

This turns every OpenArkiv submission into a **globally verifiable public record**.

---

## 🧭 Roadmap

* [ ] Mesh reliability & packet deduplication
* [ ] Beacon discovery improvements
* [ ] Advanced anonymity modes
* [ ] File chunking for large uploads
* [ ] Arkiv dashboard for submissions
* [ ] NGO & journalist tooling

---

## 🤝 Contributing

We welcome:

* Mesh protocol hackers
* E2EE & ZK engineers
* Mobile developers
* Human rights tech contributors

Ping us if you'd like to help build censorship-resistant infrastructure.

---

## 📜 License

Open source license will be specified soon.

---

## 🙏 Acknowledgements

* **BitChat** for the pioneering offline mesh architecture
* **xxDK** for privacy and metadata protection
* **Arkiv** for decentralized, verifiable data infrastructure

---
