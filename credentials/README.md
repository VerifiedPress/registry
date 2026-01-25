# Verifiable Credentials
Verifiable credentials can be used to securely prove claims—like identity, affiliation, qualifications, or reputation—across decentralized systems. Here's a breakdown of how to use them effectively:

---

### 📥 Issuance
- You receive a credential from a trusted **issuer** (like VerifiedPress) in JSON format.
- It includes structured claims (e.g. your role, name, DID) and a cryptographic **proof** (signature).

---

### 🎒 Storage
- Store your credential in a **wallet** (browser-based, mobile app, or server-side DB).
- Example tools: [did-wallet-js](https://github.com/decentralized-identity/did-wallet), Self-Sovereign Identity libraries, or a custom VC store.

---

### 🧾 Presentation
- When needed (e.g. applying for media access), you present your credential to a **verifier**.
- This can be done by:
  - Sharing the raw VC file
  - Using **Verifiable Presentation (VP)** format
  - Posting it to a verification endpoint (API)

---

### 🔒 Verification
The verifier checks:
- The credential is **valid** and signed by a trusted issuer
- The **signature** matches the issuer’s public key
- The **credentialSubject** matches the identity presenting it
- It hasn't been tampered with, expired, or revoked

---

### ⚙️ Example Verification Workflow (PHP or Node)
- Load VC JSON
- Canonicalize it (if LD-Proof)
- Verify digital signature
- Resolve issuer DID document (to get public key)
- Confirm `proofPurpose`, `issuanceDate`, and content

---
