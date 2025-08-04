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
cd pipe
```
Install pipe-cli globally on your system
```
cargo install --path ~/pipe/
```
```
export PATH="$HOME/.cargo/bin:$PATH"
echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc
```
Apply changes
```
source ~/.bashrc
```
### Firestarter Usage
**`Note`**: Firestarter commands use kebab-case (e.g., `new-user`, `upload-file`)

Showing you how to setup your account, explore all other features of the `CLI` yourself, they are pretty easy to use 🫡

Test the CLI
```
pipe
```
You should get this below
<img width="400" height="400" alt="Screenshot 2025-08-04 134232" src="https://github.com/user-attachments/assets/ba713ede-9e65-441e-98ad-ef3f23e6c90f" />

Create a new user: replace `<your_username>` with a username of choice and when prompted input a password, don't lose it!!
```
pipe new-user <your_username>
```
Login with username and password
```
pipe login <your_username>
```

> Extract your Solana `pubkey` from when you first registered as a `new-user`, go to [Solana Devnet Faucet](https://faucet.solana.com/), connect your github and claim enough faucet for testing (5 $SOL -is what I always get)

Now that you have gotten some tokens, you can now make uploads, downloads, encryptions and decryptions, etc.

Register your referrer and generate your referral code. You can use mine `DEEANALY-J7XZ`
```
pipe referral apply DEEANALY-J7XZ
```
Generate your referral code and share with friends willing to test this out.
```
pipe referral generate
```
Swap $SOL for $PIPE tokens which would be the means of payment for uploading, encrypting, etc. (Swap amount e.g 0.5, 1, 2...)
```
pipe swap-sol-for-pipe <amount>
```
##### Things to Note Before Firstarter test Operations
- For every file or folder you want to perform any actions on for which Firestarter was built, make sure the file is in the `pipe` folder before you perform the operation.
- You must rename the file.
- You must understand how file or folder paths work on Linux and how to represent them.
