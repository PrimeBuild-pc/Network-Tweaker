<p align="center">
  <h1 align="center">Network Tweaker PB</h1>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Version-3.8-blue.svg?style=flat-square" alt="Version" />
  <img src="https://img.shields.io/badge/PowerShell-5.1%2B-5e5eff.svg?style=flat-square" alt="PowerShell" />
  <img src="https://img.shields.io/badge/Windows-10%20%26%2011-0078D6.svg?style=flat-square" alt="Windows" />
  <img src="https://img.shields.io/badge/License-Personal%20Use-success.svg?style=flat-square" alt="License" />
</p>

<p align="center">
  <strong>Un tweaker avanzato per la rete su Windows 10/11</strong><br>
  Ottimizzato per gaming competitivo e latenza minima
</p>

<p align="center">
  <em>ACK immediati • BBR2 • RSC • RSS pinning • QoS per-game • Zero throttling</em>
</p>

> Backup automatico completo (JSON + .reg + punto di ripristino sistema)

---

<p align="center">
  <strong>Esecuzione in un solo comando</strong>
</p>

```powershell
irm https://github.com/PrimeBuild-pc/Network-Tweaker/raw/main/Network_Tweaker_PB.ps1 | iex
```

> Richiede **PowerShell come Amministratore**

---

### Funzionalità principali

| Categoria             | Descrizione                                                                 |
|-----------------------|-------------------------------------------------------------------------------|
| **TCP Gaming Preset** | ACK immediati, Nagle off, DelAckTicks = 0 su tutte le schede                 |
| **TCP Global**        | Preset SAFE / BALANCED / AGGRESSIVE (BBR2, ECN, autotuning off, RTO 1000ms) |
| **NIC Extras**        | RSC On, Flow Control Off, Interrupt Moderation Low                          |
| **RSS & MSI**         | Forzatura MSI + pinning su core veloci                                       |
| **QoS per gioco**     | Priorità DSCP 46 + 802.1p per CS2, Valorant, Fortnite, COD, BF6, ecc.       |
| **NDIS/MMCSS**        | NetworkThrottlingIndex = 0xFFFFFFFF • SystemResponsiveness = 0              |
| **Security**          | Blocco SMBv1, NetBIOS, mDNS, RDP (modalità SAFE / ADVANCED)                 |
| **Backup & Restore**  | Snapshot completo + esportazione .reg + restore point automatico            |

---

<p align="center">
  <img src="https://github.com/user-attachments/assets/a7db4c6b-aaf7-4b0a-8a6d-3f6ed98bd4f3" alt="Network Tweaker PB GUI" width="800" />
  <br><br>
  <em>Interfaccia grafica semplice e potente</em>
</p>

---

### Compatibilità

- Windows 10 22H2 • Windows 11 (tutte le edizioni)  
- Realtek 8111/8125/8126 • Intel I225/I226 • Killer • AQC107 • e molte altre

---

### Crediti

Realizzato e mantenuto da **PrimeBuild**  
Basato su uno script originale della community (autore sconosciuto) e completamente espanso

Progetto open-source • Uso libero per scopi personali  
Non ridistribuire versioni modificate senza autorizzazione

---
<p align="center">
  Ottimizza la tua rete. Gioca senza compromessi.
</p>
