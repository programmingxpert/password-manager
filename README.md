# Secure Password Manager 🔒

A lightweight, local-first password manager built with Next.js.

All your passwords are encrypted with AES-256 (military-grade encryption) and stored locally on your device — no cloud, no servers, and no third parties involved.

## ✨ Features

*   **AES-256 Encryption:** All stored passwords are encrypted using industry-standard AES-256.
*   **Master Password Protection:** Your encryption key is derived using PBKDF2 with 100,000 iterations for maximum security against brute-force attacks.
*   **Local Storage Only:** Your data never leaves your device; it's stored securely in your browser's local storage.
*   **Offline-first:** Works entirely without an internet connection after the initial load.
*   **Simple, Clean UI:** Easy-to-use interface with dark mode support.
*   **Open Source:** The codebase is fully transparent and available for review.

## 🔒 How It Works

1.  Your **Master Password** is used to generate an encryption key.
2.  Passwords are encrypted locally using **AES-256**.
3.  The encryption key is derived via **PBKDF2** (Password-Based Key Derivation Function 2) with **100,000 iterations** to resist brute-force attacks.
4.  **No passwords, master keys, or sensitive data are ever sent over the internet** — everything remains 100% on your machine.

**Important Security Notice:** This application does **NOT** save your master password in the browser's autofill or password manager. Any attempt to save your master password using browser features is done **at your own risk** and is **highly discouraged**. Your master password should be kept secure and not stored in ways that could be easily accessed.

## 🛠️ Built With

*   [**Next.js**](https://nextjs.org/) — React Framework
*   [**Tailwind CSS**](https://tailwindcss.com/) — For styling
*   [**Lucide Icons**](https://lucide.dev/) — Icon pack
*   [**Framer Motion**](https://www.framer.com/motion/) — Smooth animations
*   [**Radix UI**](https://www.radix-ui.com/) — Accessible UI components

## 🚀 Getting Started

1.  Clone the repository:

    ```bash
    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
    ```

2.  Install dependencies:

    ```bash
    npm install
    # or
    yarn install
    ```

3.  Run the development server:

    ```bash
    npm run dev
    # or
    yarn dev
    ```

    Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

## 📄 License

This project is licensed under the MIT License.

## 📌 Tags

`AES-256` • `Local Storage` • `PBKDF2` • `Master Password` • `Offline Security` • `Encryption` • `Password Manager` • `Data Privacy` • `Next.js`
