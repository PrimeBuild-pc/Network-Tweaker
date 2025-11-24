# Network Tweaker

Strumento PowerShell per applicare rapidamente ottimizzazioni di rete e driver su Windows, con un focus particolare sulla riduzione della latenza e sulla disattivazione delle funzioni di risparmio energetico troppo aggressive.

## Power saving features
La sezione esistente dedicata ai power saving nel tool ora include (o può essere estesa con) i seguenti gruppi di opzioni globali:

### A) Disable NIC Power Saving (Windows Power Manager)
- Registry: `HKLM\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\{e73a048d-bf27-4f12-9731-8b2076e8891f}\{12bbebe6-58d1-4c48-9d77-a8fba65c2d5e}`
- Rappresenta l'opzione **Allow the computer to turn off this device to save power**.
- Comandi utili: `powercfg -devicequery wake_armed` e `powercfg -devicedisablewake "Nome scheda"`.
- Toggle aggiuntivi suggeriti: **Allow device to sleep** (on/off) e **Allow wake** (on/off).

### B) PCI Express ASPM (L1, L1.1, L1.2)
- Registry: `HKLM\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\{501a4d13-42af-4429-9fd1-a8218c268e20}` sotto *Link State Power Management*.
- Impatto: disattivare gli stati L1 deep riduce le latenze, utile per il gaming.

### C) Global Network Throttling (MMCSS)
- Registry: `HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile`
- Chiavi: `NetworkThrottlingIndex`, `SystemResponsiveness`.
- Impatto: previene il throttling MMCSS sul traffico rete in foreground/background.

### D) TCP Auto-Tuning & Congestion Providers
- Comando/Regedit: `netsh int tcp set global autotuninglevel=...` e chiavi in `HKLM\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`.
- Chiave utile: `EnablePMTUBHDetect` (PMTU discovery) per controllare il comportamento di scaling del network stack.

### E) NIC Selective Suspend
- Registry: `HKLM\SYSTEM\CurrentControlSet\Services\NDIS\Parameters`
- Chiavi: `DefaultSelectiveSuspend`, `EnableSelectiveSuspend` (per dispositivo).
- Impatto: evita che Windows sospenda aggressivamente la NIC causando lag/jitter; aggiungere il toggle **Selective Suspend → Disabled**.

### F) Power Saving Mode on NDIS 6.x
- Registry: `HKLM\SYSTEM\CurrentControlSet\Services\NDIS\Parameters`
- Chiavi: `IdlePowerSaver`, `ReductionInReceiveBufferDuringLowPower`, `ReductionInSendBufferDuringLowPower`, `EnableNDISPowerManagement`.
- Impatto: controllano le ottimizzazioni energetiche lato NDIS su Windows 10+.

### G) Modern Standby (S0ix) NIC power behavior
- Registry: `HKLM\SYSTEM\CurrentControlSet\Control\Power`
- Chiavi: `PlatformAoAcOverride`, `CsEnabled`.
- Impatto: influenza il comportamento della NIC in S0 low-power (problemi di wake ecc.).

## Raccomandazioni da integrare
Oltre alle funzioni già presenti (power saving driver-level, green ethernet toggle, flow control, EEE), sono consigliati quattro toggle globali:
1. **NIC Selective Suspend (globale)** – `HKLM\SYSTEM\CurrentControlSet\Services\NDIS\Parameters` → `DefaultSelectiveSuspend = 0` per impedire la sospensione della NIC.
2. **PCI Express Link State Power Management (ASPM)** – `PowerSettings\{501a4d13-42af-4429-9fd1-a8218c268e20}` per evitare gli stati L1 deep.
3. **Disabilitare "Allow computer to turn off this device to save power"** – via `powercfg -devicedisablewake` e `Set-NetAdapterPowerManagement -NoPowerSaving On`.
4. **Network Throttling Index** – `HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile` → `NetworkThrottlingIndex = ffffffff` per eliminare il throttling MMCSS.
