# **PhasePass**

**The Dynamic, Evolving Password Manager**  
_Military-inspired security. Always one step ahead._

---

## What is **PhasePass**?

**PhasePass** is a next-generation password manager inspired by modern cyber operations and elite security standards. Built with Delphi (FMX), it redefines password protection by moving beyond static secrets—using dynamic, recipe-based authentication and future-ready self-mutation.

Whether you’re a developer, a security professional, or anyone who wants mission-level privacy, PhasePass is designed to keep your secrets safe—no matter how the threat landscape changes.

---

## Key Features

- **Dynamic "Recipe" Authentication**  
  Build your own sequence of tokens (clock, date, random values, battery, SSID, etc.) and static text to create passwords that change with every login.

- **Evolving Security**  
  Optional mutation engine rotates encryption keys based on atomic clock, environment, or custom triggers, making brute-force and forensics nearly impossible.

- **Encrypted Vault (SQLite + AES-256)**  
  Military-grade encryption, easy backup and restore, with the option for self-destructing "live vaults" for critical, short-term secrets.

- **Cascading Vault Encryption (Planned)**
  - Wrap your encrypted SQLite vault with multiple, user-chosen AES-256 layers.
  - Each layer can have its own dynamic token/recipe, making brute-force and forensic attacks exponentially harder.
  - Optional: Quick access with outer layers, full access requires all tokens.

- **Single-Use Passwords (Planned)**
  - Mark any credential as “single-use” for disposable logins or secure sharing.
  - Once revealed, copied, or used, the password self-deletes from the vault.
  - Perfect for guest access, emergency logins, or sharing temporary secrets.

- **Multi-Platform (Planned)**  
  Windows-first (Delphi FMX), with Android support to follow.

- **Open Source, Modern Design**  
  Built to invite community contributions, peer review, and transparent security.

---

## Feature Comparison

| Feature                      | PhasePass         | Bitwarden   | KeePass   | LastPass  | 1Password |
|------------------------------|------------------|-------------|-----------|-----------|-----------|
| Dynamic, recipe-based auth   | 🟢 Yes           | 🔴 No       | 🔴 No     | 🔴 No     | 🔴 No     |
| Multi-layer (onion) encryption| 🟡 Planned       | 🔴 No       | 🟡 Partial*| 🔴 No     | 🔴 No     |
| Self-mutating vault          | 🟡 Planned       | 🔴 No       | 🔴 No     | 🔴 No     | 🔴 No     |
| Single-use (self-deleting) passwords | 🟡 Planned | 🔴 No | 🔴 No | 🔴 No | 🔴 No |
| Open source                  | 🟢 Yes           | 🟢 Yes      | 🟢 Yes    | 🔴 No     | 🔴 No     |
| Cross-platform (Win/Android) | 🟡 Planned       | 🟢 Yes      | 🟢 Yes    | 🟢 Yes    | 🟢 Yes    |
| Hardware key/2FA support     | 🟡 Planned¹      | 🟢 Yes      | 🟡 Plugins| 🟢 Yes    | 🟢 Yes    |
| One-time sharing             | 🟡 Planned       | 🟢 Yes      | 🟡 Plugin | 🟢 Yes    | 🟢 Yes    |
| Custom field/token system    | 🟢 Yes           | 🟡 Limited  | 🟡 Plugin | 🟡 Limited| 🟡 Limited|
| Self-destruct/vault wipe     | 🟡 Planned       | 🔴 No       | 🔴 No     | 🔴 No     | 🔴 No     |
| Android "Live Vault" (Foreground Service, self-destruct on tamper/reboot) | 🟡 Planned | 🔴 No | 🔴 No | 🔴 No | 🔴 No |

¹ Requires internet or supported hardware for full 2FA functionality.

\*KeePass can be used with encrypted containers (e.g., VeraCrypt) for multi-layer security, but it is not native to KeePass.

---

## Roadmap

_**PhasePass** is in early development—here’s what’s planned:_

- [ ] Windows app (FMX) with core dynamic recipe/token authentication
- [ ] Drag-and-drop password building UI
- [ ] AES-256 encrypted local storage (SQLite, SQLCipher, or SEE)
- [ ] User hints and help for recipe creation
- [ ] Backup/restore functionality
- [ ] Android version (FMX)
- [ ] Self-mutation: periodic or triggered re-encryption (“mutation engine”)
- [ ] Live vault mode: RAM-only, self-destruct on tamper or reboot
- [ ] One-time password/guest share with auto-delete
- [ ] Advanced: atomic clock/NTP support for key rotation
- [ ] Full documentation, threat model, and security audit
- [ ] Android "Live Vault": as as Foreground Service that self-destructs on tamper or reboot (planned)
- [ ] PhasePass FileVault: Dedicated, multi-layer encrypted storage for files and documents (planned)
- [ ] Active Threat Defense: Monitor system processes during vault access; terminate or prevent startup if suspicious/unknown apps are detected (research/planned)

<details>
<summary><strong>What is a foreground service?</strong></summary>

Android "Live Vault" runs as a Foreground Service, meaning it stays active and protected while in use. If the app is tampered with, moved to the background, or if the device reboots, the vault immediately self-destructs—ensuring sensitive data never lingers unprotected.

</details>

### PhasePass Server (Planned)

To support advanced 2FA features (SMS, email, push), PhasePass will offer an optional self-hosted server. The first version will run on Windows, built with Delphi, and allow users to host their own secure code generation and delivery backend. Future versions may include Linux or cross-platform support.

### Limitations & Security Notes

- **Android OS Restrictions:** While Live Vault runs as a Foreground Service, modern Android versions may still terminate services under certain conditions (e.g., extreme battery saving, user-initiated force-stop). If the service is killed, the app attempts to wipe sensitive data, but absolute guarantees cannot be made.
- **Reboot Handling:** The vault will self-destruct on device reboot if possible, but delays may occur depending on device manufacturer and OS version.
- **Rooted Devices & Advanced Attackers:** On rooted or compromised devices, determined attackers may bypass app protections or access encrypted data stored on disk.
- **User Experience:** Users must not dismiss the Foreground Service notification, force close the app, or switch away during Live Vault mode unless prepared for vault destruction.
- **No Undelete:** Once the Live Vault is wiped or self-destructs, the data cannot be recovered.

**PhasePass** is designed for advanced users who need maximum security and are aware of the inherent risks and trade-offs.


Have ideas? See [issues](../../issues) or start a discussion!
We welcome feedback, suggestions, and contributors of all skill levels—help us shape the future of password security!

---

## Why **PhasePass**?

> _Inspired by the military concept of "phases" and the relentless pursuit of security by cyber operations specialists, **PhasePass** is always evolving—never static, never predictable._

---

## Status

**🚧 In active planning — development will begin soon. Follow or star this repo for updates!**

---

## License

[MIT License](LICENSE)

---

## Contact

Have feedback, want to contribute, or just want to learn more?
- Open an issue or discussion here on GitHub.
- Project lead: [War3Evo (Greg Timmons)](https://timmons.pro)

## Support **PhasePass**

If **PhasePass** or my work helps you, consider supporting development:  
[paypal.me/timmonspro](https://www.paypal.com/paypalme/timmonspro)

---

_**PhasePass** is not affiliated with any military or government agency. Inspired by best practices in cybersecurity, but built for everyone._
