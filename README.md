<!DOCTYPE html>

<html lang="en">

<head>

&nbsp;   <meta charset="UTF-8">

&nbsp;   <meta name="viewport" content="width=device-width, initial-scale=1.0">

&nbsp;   <title>PrimeBuild Network Tweaker</title>

&nbsp;   <meta name="description" content="Advanced Network Adapter Optimization Utility for Windows. TCP/IP, RSS, QoS, and Driver Latency Tweaks.">

&nbsp;   <style>

&nbsp;       :root {

&nbsp;           --bg-color: #171717;

&nbsp;           --surface-color: #202020;

&nbsp;           --text-primary: #ffffff;

&nbsp;           --text-secondary: #a0a0a0;

&nbsp;           --accent-color: #4a90e2;

&nbsp;           --code-bg: #111111;

&nbsp;           --success-color: #1ec38b;

&nbsp;       }



&nbsp;       \* {

&nbsp;           box-sizing: border-box;

&nbsp;           margin: 0;

&nbsp;           padding: 0;

&nbsp;       }



&nbsp;       body {

&nbsp;           font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;

&nbsp;           background-color: var(--bg-color);

&nbsp;           color: var(--text-primary);

&nbsp;           line-height: 1.6;

&nbsp;           display: flex;

&nbsp;           flex-direction: column;

&nbsp;           min-height: 100vh;

&nbsp;           align-items: center;

&nbsp;           justify-content: center;

&nbsp;       }



&nbsp;       .container {

&nbsp;           width: 90%;

&nbsp;           max-width: 800px;

&nbsp;           padding: 2rem;

&nbsp;           text-align: center;

&nbsp;       }



&nbsp;       h1 {

&nbsp;           font-size: 3rem;

&nbsp;           font-weight: 700;

&nbsp;           letter-spacing: -1px;

&nbsp;           margin-bottom: 0.5rem;

&nbsp;           background: linear-gradient(135deg, #fff 0%, #a5a5a5 100%);

&nbsp;           -webkit-background-clip: text;

&nbsp;           -webkit-text-fill-color: transparent;

&nbsp;       }



&nbsp;       p.subtitle {

&nbsp;           color: var(--text-secondary);

&nbsp;           font-size: 1.2rem;

&nbsp;           margin-bottom: 3rem;

&nbsp;       }



&nbsp;       .cmd-wrapper {

&nbsp;           background-color: var(--code-bg);

&nbsp;           border: 1px solid #333;

&nbsp;           border-radius: 12px;

&nbsp;           padding: 1.5rem;

&nbsp;           position: relative;

&nbsp;           margin-bottom: 4rem;

&nbsp;           text-align: left;

&nbsp;           box-shadow: 0 10px 30px rgba(0,0,0,0.3);

&nbsp;           transition: border-color 0.3s ease;

&nbsp;       }



&nbsp;       .cmd-wrapper:hover {

&nbsp;           border-color: var(--accent-color);

&nbsp;       }



&nbsp;       code {

&nbsp;           font-family: 'Consolas', 'Monaco', 'Courier New', monospace;

&nbsp;           color: var(--accent-color);

&nbsp;           font-size: 0.95rem;

&nbsp;           word-break: break-all;

&nbsp;       }



&nbsp;       .copy-btn {

&nbsp;           position: absolute;

&nbsp;           right: 15px;

&nbsp;           top: 50%;

&nbsp;           transform: translateY(-50%);

&nbsp;           background-color: var(--surface-color);

&nbsp;           border: 1px solid #444;

&nbsp;           color: var(--text-primary);

&nbsp;           padding: 8px 16px;

&nbsp;           border-radius: 6px;

&nbsp;           cursor: pointer;

&nbsp;           font-size: 0.85rem;

&nbsp;           transition: all 0.2s ease;

&nbsp;       }



&nbsp;       .copy-btn:hover {

&nbsp;           background-color: var(--accent-color);

&nbsp;           border-color: var(--accent-color);

&nbsp;           color: white;

&nbsp;       }



&nbsp;       .features-grid {

&nbsp;           display: grid;

&nbsp;           grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));

&nbsp;           gap: 2rem;

&nbsp;           text-align: left;

&nbsp;           margin-bottom: 4rem;

&nbsp;       }



&nbsp;       .feature-item h3 {

&nbsp;           color: var(--text-primary);

&nbsp;           font-size: 1.1rem;

&nbsp;           margin-bottom: 0.5rem;

&nbsp;       }



&nbsp;       .feature-item p {

&nbsp;           color: var(--text-secondary);

&nbsp;           font-size: 0.9rem;

&nbsp;       }



&nbsp;       footer {

&nbsp;           margin-top: auto;

&nbsp;           color: var(--text-secondary);

&nbsp;           font-size: 0.8rem;

&nbsp;           padding: 2rem;

&nbsp;       }



&nbsp;       footer a {

&nbsp;           color: var(--text-secondary);

&nbsp;           text-decoration: none;

&nbsp;           border-bottom: 1px dotted var(--text-secondary);

&nbsp;       }



&nbsp;       footer a:hover {

&nbsp;           color: var(--accent-color);

&nbsp;           border-bottom-color: var(--accent-color);

&nbsp;       }



&nbsp;       /\* Mobile adjustments \*/

&nbsp;       @media (max-width: 600px) {

&nbsp;           h1 { font-size: 2rem; }

&nbsp;           .copy-btn { position: static; display: block; width: 100%; margin-top: 15px; transform: none; }

&nbsp;           .cmd-wrapper { text-align: center; }

&nbsp;       }

&nbsp;   </style>

</head>

<body>



&nbsp;   <div class="container">

&nbsp;       <h1>Network Tweaker</h1>

&nbsp;       <p class="subtitle">Advanced Network Adapter Optimization \& Diagnostics Utility</p>



&nbsp;       <div class="cmd-wrapper">

&nbsp;           <code id="cmd">irm https://raw.githubusercontent.com/PrimeBuild-pc/Network-Tweaker/main/Network\_Tweaker\_PB.ps1 | iex</code>

&nbsp;           <button class="copy-btn" onclick="copyCmd()">Copy Command</button>

&nbsp;       </div>



&nbsp;       <div class="features-grid">

&nbsp;           <div class="feature-item">

&nbsp;               <h3>⚡ RSS \& Interrupts</h3>

&nbsp;               <p>Advanced Receive Side Scaling (RSS) configuration, MSI Mode enabling, and CPU affinity pinning.</p>

&nbsp;           </div>

&nbsp;           <div class="feature-item">

&nbsp;               <h3>🎮 Gaming QoS</h3>

&nbsp;               <p>Pre-configured QoS policies for low-latency gaming (DSCP/Priority) and Nagle's Algorithm toggles.</p>

&nbsp;           </div>

&nbsp;           <div class="feature-item">

&nbsp;               <h3>🛡️ Security Hardening</h3>

&nbsp;               <p>One-click hardening: Disable SMBv1, NetBIOS, LLMNR, and restrict unneeded services.</p>

&nbsp;           </div>

&nbsp;           <div class="feature-item">

&nbsp;               <h3>🔧 TCP/IP Offloads</h3>

&nbsp;               <p>Fine-tune Checksum Offloads, RTO, Congestion Providers (CUBIC/BBR2), and Auto-Tuning logic.</p>

&nbsp;           </div>

&nbsp;           <div class="feature-item">

&nbsp;               <h3>🔋 Power Management</h3>

&nbsp;               <p>Control NIC power states, PCIe ASPM, and Selective Suspend to prevent latency spikes.</p>

&nbsp;           </div>

&nbsp;           <div class="feature-item">

&nbsp;               <h3>📊 Diagnostics</h3>

&nbsp;               <p>Built-in tools for MTU calculation, Bufferbloat testing, Latency monitoring, and Backup/Restore.</p>

&nbsp;           </div>

&nbsp;       </div>

&nbsp;   </div>



&nbsp;   <footer>

&nbsp;       <p>Use at your own risk. Requires Administrator privileges.</p>

&nbsp;       <p>\&copy; 2024 <a href="https://github.com/PrimeBuild-pc">PrimeBuild-pc</a></p>

&nbsp;   </footer>



&nbsp;   <script>

&nbsp;       function copyCmd() {

&nbsp;           const cmdText = document.getElementById('cmd').innerText;

&nbsp;           navigator.clipboard.writeText(cmdText).then(() => {

&nbsp;               const btn = document.querySelector('.copy-btn');

&nbsp;               const originalText = btn.innerText;

&nbsp;               

&nbsp;               btn.innerText = "Copied!";

&nbsp;               btn.style.backgroundColor = "var(--success-color)";

&nbsp;               btn.style.borderColor = "var(--success-color)";

&nbsp;               

&nbsp;               setTimeout(() => {

&nbsp;                   btn.innerText = originalText;

&nbsp;                   btn.style.backgroundColor = "";

&nbsp;                   btn.style.borderColor = "";

&nbsp;               }, 2000);

&nbsp;           });

&nbsp;       }

&nbsp;   </script>

</body>

</html>

