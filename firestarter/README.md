## Pipe Firestarter

What is the Pipe Firestarter? - A powerful command-line interface for interacting with the Pipe distributed storage network.

Features
- Decentralized Storage: Upload and download files to/from the Pipe network
- Directory Sync: Intelligent sync with .pipe-sync metadata tracking and incremental updates
- Client-Side Encryption: AES-256-GCM encryption with password-based key derivation
- Quantum-Resistant Encryption: Post-quantum cryptography using Kyber-1024 (ML-KEM) and Dilithium5 (ML-DSA)
- Tiered Upload System: Multiple upload tiers with different performance characteristics
- Directory Operations: Upload entire directories with progress tracking
- Resumable Uploads: Skip already uploaded files with --skip-uploaded
- JWT Authentication: Secure authentication with JWT tokens
- Service Discovery: Automatic selection of optimal storage nodes
- Multiple Account Support: Manage multiple accounts with custom config files
- Local Key Management: Generate and manage encryption keys locally with built-in keyring
- Blake3 File IDs: Every file gets a unique Blake3 hash ID for content-based addressing
- Integrity Verification: Automatic integrity checking using Blake3 hashes
---
### Auto Installation
```
bash <(curl -sSL https://raw.githubusercontent.com/pipenetwork/pipe/main/setup.sh)
```
### Manually Installation
