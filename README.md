# Secure Local Password Manager

A lightweight, zero-knowledge, client-side password vault that runs 100% locally in your browser. All credentials are encrypted on your device and are never transmitted to any server.

---

## Security Architecture

The application implements a strict zero-trust model using the browser's native **Web Crypto API**:

```
[Master Password] ---> [PBKDF2 Key Derivation (100k+ iterations, Salt)] 
                               |
                               v
                       [AES-GCM 256-bit Key]
                               |
                               +---> Encrypts credentials (using unique IV)
                               |
                               v
                     [Encrypted LocalStorage Ciphertext]
```

### 1. Key Derivation (PBKDF2)
Your master password is never stored. Instead, it is run through the **PBKDF2** (Password-Based Key Derivation Function 2) using `SHA-256` and a locally generated salt with a high iteration count. This derives a secure 256-bit key used for encryption.

### 2. Encryption Standard (AES-GCM)
All credential payloads are encrypted using **AES-GCM 256-bit** (Advanced Encryption Standard in Galois/Counter Mode). Each encryption operation utilizes a unique initialization vector (IV) to prevent replay attacks and ensure cryptographic confidentiality and integrity.

### 3. Storage
The resulting ciphertext, IV, and salt are stored in the browser's `localStorage`. Decryption happens entirely in volatile memory when you unlock the vault with your master password.

---

## Key Features

- **Zero Server Footprint**: No servers, no user accounts, and zero data leaks.
- **Strong Cryptography**: End-to-end local encryption using browser standards.
- **Password Generator**: Custom entropy-based local password generator with configurable length and character sets.
- **Search & Organize**: Live search-as-you-type filtering for username, website, and tags.
- **Import/Export**: Backup your encrypted vault as a JSON file or export decrypted credentials for migrating to other systems.
- **Premium Aesthetics**: Elegant, responsive glassmorphism user interface designed with JetBrains Mono and Anybody typography, featuring native dark-mode optimization.

---

## Usage & Deployment

### Running Locally
Since the application consists of a static file interface, you can serve it locally using any static web server:
1. Clone the repository:
   ```bash
   git clone https://github.com/programmingxpert/password-manager.git
   cd password-manager
   ```
2. Double-click `index.html` or serve it locally:
   ```bash
   npx serve .
   ```

### Hosting on GitHub Pages
To host this secure vault on your own domain:
1. Enable GitHub Pages in your repository settings.
2. Select the `main` branch root as your Pages source.

---

## Author

**Satya**  
GitHub: [programmingxpert](https://github.com/programmingxpert/)
