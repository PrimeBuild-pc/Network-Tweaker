# Network Tweaker PB

![Version](https://img.shields.io/badge/Version-3.8-blue.svg)
![PowerShell](https://img.shields.io/badge/PowerShell-5.1%2B-5e5eff.svg)
![Windows](https://img.shields.io/badge/Windows-10%20%26%2011-0078D6.svg)
![License](https://img.shields.io/badge/License-Free%20for%20personal%20use-success.svg)

Un tweaker avanzato per scheda di rete su Windows 10/11, progettato per **gaming competitivo** e latenza minima.

Ottimizza in un click:
- TCP Stack (BBR2, ECN, RTO, autotuning)
- ACK immediati (TcpAckFrequency=1, TCPNoDelay=1)
- RSC / Flow Control / Interrupt Moderation
- RSS + MSI Interrupt pinning
- QoS per-game (Fortnite, CS2, Valorant, COD, BF6, ecc.)
- NDIS/MMCSS (NetworkThrottlingIndex = 0xFFFFFFFF)
- Blocco SMB/NetBIOS/mDNS/RDP (modalità SAFE/ADVANCED)

> Include backup automatico e restore completo (JSON + .reg + restore point)

---

### Esecuzione rapida (one-liner)

```powershell
irm https://github.com/PrimeBuild-pc/Network-Tweaker/raw/main/Network_Tweaker_PB.ps1 | iex
```

> Richiede **PowerShell eseguito come Amministratore**

---

### Funzionalità principali

| Categoria               | Cosa fa                                                                 |
|-------------------------|--------------------------------------------------------------------------|
| **TCP Gaming Preset**   | ACK immediati + Nagle off + DelAckTicks=0 su tutte le schede            |
| **TCP Global**          | SAFE / BALANCED / AGGRESSIVE (BBR2, ECN, RTO 1000ms, autotuning off)    |
| **NIC Extras**          | RSC On, Flow Control Off, Interrupt Moderation Low                     |
| **RSS & MSI**           | Forzatura MSI + affinity su core veloci                                 |
| **QoS per gioco**       | Priorità DSCP 46 + 802.1p per CS2, Valorant, Fortnite, ecc.            |
| **NDIS/MMCSS**          | Disabilita throttling rete e dà priorità massima ai processi multimediali |
| **Security**            | Blocca SMBv1, NetBIOS, mDNS, RDP (opzioni SAFE/ADVANCED)                |
| **Backup & Restore**    | Snapshot completo + esportazione .reg + punto di ripristino sistema     |

---

<img width="544" height="428" alt="Screenshot 2025-11-24 194111" src="https://github.com/user-attachments/assets/a7db4c6b-aaf7-4b0a-8a6d-3f6ed98bd4f3" />

---

### Compatibilità

- Windows 10 22H2 / Windows 11 (tutte le versioni)
- Realtek 8111/8125/8126, Intel I225/I226, Killer, AQC107, ecc.

---

### Crediti

Realizzato da **PrimeBuild**  
Progetto open-source, uso libero per scopi personali.  
Non ridistribuire versioni modificate senza autorizzazione.

---
```

Copia e incolla questo contenuto direttamente nel tuo `README.md` del repository.  
Se vuoi aggiungere uno screenshot reale, caricalo nella repo come `screenshot.png` (o cambiane il nome nel link).

Divertiti e buona latenza! 🚀
