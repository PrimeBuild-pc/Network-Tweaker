<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PrimeBuild Network Tweaker</title>
    <meta name="description" content="Advanced Network Adapter Optimization Utility for Windows. TCP/IP, RSS, QoS, and Driver Latency Tweaks.">
    <style>
        :root {
            --bg-color: #171717;
            --surface-color: #202020;
            --text-primary: #ffffff;
            --text-secondary: #a0a0a0;
            --accent-color: #4a90e2;
            --code-bg: #111111;
            --success-color: #1ec38b;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
            background-color: var(--bg-color);
            color: var(--text-primary);
            line-height: 1.6;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
            align-items: center;
            justify-content: center;
        }

        .container {
            width: 90%;
            max-width: 800px;
            padding: 2rem;
            text-align: center;
        }

        h1 {
            font-size: 3rem;
            font-weight: 700;
            letter-spacing: -1px;
            margin-bottom: 0.5rem;
            background: linear-gradient(135deg, #fff 0%, #a5a5a5 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        p.subtitle {
            color: var(--text-secondary);
            font-size: 1.2rem;
            margin-bottom: 3rem;
        }

        .cmd-wrapper {
            background-color: var(--code-bg);
            border: 1px solid #333;
            border-radius: 12px;
            padding: 1.5rem;
            position: relative;
            margin-bottom: 4rem;
            text-align: left;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            transition: border-color 0.3s ease;
        }

        .cmd-wrapper:hover {
            border-color: var(--accent-color);
        }

        code {
            font-family: 'Consolas', 'Monaco', 'Courier New', monospace;
            color: var(--accent-color);
            font-size: 0.95rem;
            word-break: break-all;
        }

        .copy-btn {
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            background-color: var(--surface-color);
            border: 1px solid #444;
            color: var(--text-primary);
            padding: 8px 16px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 0.85rem;
            transition: all 0.2s ease;
        }

        .copy-btn:hover {
            background-color: var(--accent-color);
            border-color: var(--accent-color);
            color: white;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            text-align: left;
            margin-bottom: 4rem;
        }

        .feature-item h3 {
            color: var(--text-primary);
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
        }

        .feature-item p {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        footer {
            margin-top: auto;
            color: var(--text-secondary);
            font-size: 0.8rem;
            padding: 2rem;
        }

        footer a {
            color: var(--text-secondary);
            text-decoration: none;
            border-bottom: 1px dotted var(--text-secondary);
        }

        footer a:hover {
            color: var(--accent-color);
            border-bottom-color: var(--accent-color);
        }

        /* Mobile adjustments */
        @media (max-width: 600px) {
            h1 { font-size: 2rem; }
            .copy-btn { position: static; display: block; width: 100%; margin-top: 15px; transform: none; }
            .cmd-wrapper { text-align: center; }
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>Network Tweaker</h1>
        <p class="subtitle">Advanced Network Adapter Optimization & Diagnostics Utility</p>

        <div class="cmd-wrapper">
            <code id="cmd">irm https://raw.githubusercontent.com/PrimeBuild-pc/Network-Tweaker/main/Network_Tweaker_PB.ps1 | iex</code>
            <button class="copy-btn" onclick="copyCmd()">Copy Command</button>
        </div>

        <div class="features-grid">
            <div class="feature-item">
                <h3>⚡ RSS & Interrupts</h3>
                <p>Advanced Receive Side Scaling (RSS) configuration, MSI Mode enabling, and CPU affinity pinning.</p>
            </div>
            <div class="feature-item">
                <h3>🎮 Gaming QoS</h3>
                <p>Pre-configured QoS policies for low-latency gaming (DSCP/Priority) and Nagle's Algorithm toggles.</p>
            </div>
            <div class="feature-item">
                <h3>🛡️ Security Hardening</h3>
                <p>One-click hardening: Disable SMBv1, NetBIOS, LLMNR, and restrict unneeded services.</p>
            </div>
            <div class="feature-item">
                <h3>🔧 TCP/IP Offloads</h3>
                <p>Fine-tune Checksum Offloads, RTO, Congestion Providers (CUBIC/BBR2), and Auto-Tuning logic.</p>
            </div>
            <div class="feature-item">
                <h3>🔋 Power Management</h3>
                <p>Control NIC power states, PCIe ASPM, and Selective Suspend to prevent latency spikes.</p>
            </div>
            <div class="feature-item">
                <h3>📊 Diagnostics</h3>
                <p>Built-in tools for MTU calculation, Bufferbloat testing, Latency monitoring, and Backup/Restore.</p>
            </div>
        </div>
    </div>

    <footer>
        <p>Use at your own risk. Requires Administrator privileges.</p>
        <p>&copy; 2024 <a href="https://github.com/PrimeBuild-pc">PrimeBuild-pc</a></p>
    </footer>

    <script>
        function copyCmd() {
            const cmdText = document.getElementById('cmd').innerText;
            navigator.clipboard.writeText(cmdText).then(() => {
                const btn = document.querySelector('.copy-btn');
                const originalText = btn.innerText;
                
                btn.innerText = "Copied!";
                btn.style.backgroundColor = "var(--success-color)";
                btn.style.borderColor = "var(--success-color)";
                
                setTimeout(() => {
                    btn.innerText = originalText;
                    btn.style.backgroundColor = "";
                    btn.style.borderColor = "";
                }, 2000);
            });
        }
    </script>
</body>
</html>
