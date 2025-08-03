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
#### Prerequisites
To build make sure you have the below system packages installed
```
sudo apt update && sudo apt upgrade -y
sudo apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y
```
Install Rust
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source "$HOME/.cargo/env"
```
You will be prompted to choosean installation method, press `Enter` on your keyboard to use Default installation process.

#### Installation
Use an of the methods you prefer
##### Option 1: Download Pre-built binaries 
(Linux/MacOS)
```
# Download the binary (replace URL with your platform's binary)
wget https://github.com/PipeNetwork/pipe/releases/latest/download/pipe-linux-amd64

# Make it executable
chmod +x pipe-linux-amd64

# Move to PATH
sudo mv pipe-linux-amd64 /usr/local/bin/pipe

# Verify installation
pipe --version
```
(Windows) - Not recommended as I couldn't find the binary for Windows
1. Download `pipe-windows-amd64.exe` from the releases page.
2. Rename as `pipe.exe`.
3. Add it to your `PATH` or run it directly from the command prompt (cmd).

##### Option 2: Install from Source (Recommended for Ubuntu WSL or VPS)
Clone the repository
```
git clone https://github.com/PipeNetwork/pipe.git
cd pipe/pipe-cli
```
Install pipe-cli globally on your system
```
cargo install --path .
```
```
export PATH="$HOME/.cargo/bin:$PATH"
echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc
```
Apply changes
```
source ~/.bashrc
```
