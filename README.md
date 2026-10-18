![OpenCrawl Logo](https://openclaw.ai/og-image.png)

# Deploy and Host OpenClaw Railway Template on Railway

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/deploy/openclaw-railway-t-1?referralCode=QXdhdr&utm_medium=integration&utm_source=template&utm_campaign=generic)

**OpenClaw** is a self-hosted AI agent framework that can execute commands, manage files, and perform tasks autonomously based on user instructions. This template deploys OpenClaw on Railway with minimal configuration, allowing you to run and access it remotely without managing servers. 🤖⚙️

## 🚀 Quick Start Deployment Guide

### Step 1: Deploy on Railway

1. Click the **"Deploy on Railway"** button at the top of this page &amp; wait for the initial deployment to complete. The first startup can take several minutes

### Step 2: Note Your Credentials

Check the **Variables** tab and save following:

- **SETUP_PASSWORD**: Your password for accessing the setup wizard

⚠️ **Keep this secure!** You'll need this in the next steps.

### Step 3: Access Setup Wizard

1. Click on the URL provided by Railway in your project dashboard (e.g., `https://your-app-xyz.up.railway.app`)
2. Login prompt appears:
   - **Username**: Leave blank 
   - **Password**: Enter your `SETUP_PASSWORD`

### Step 4: Complete the Setup Wizard

1. Select your **provider & auth type**, then enter an API key if requested.
2. Add **channels** if you want to use Telegram, Discord, or Slack. This is optional.
3. Click **Run Setup**. For browser sign-in, open the sign-in URL and enter the code shown by the wizard; keep the setup page open until it completes.
4. Click **Open OpenClaw UI**. If it is still starting, wait for the Gateway to become ready.
5. If OpenClaw asks for a **Gateway secret**, return to `/setup`, click **Copy Gateway Token**, paste it into that field, and click **Connect**.
6. If OpenClaw shows **Approve this browser** or a command such as `openclaw devices approve <requestId>`, keep that tab open. Return to `/setup` → **Pair Devices** → **Approve** the request with the same ID. Then return to OpenClaw; it connects automatically, or you can click **Check now**.
7. Once OpenClaw shows **Connected**, you can start chatting.

For Telegram or Discord, message your bot. If it replies with a pairing code, go to `/setup` → **Approve Channel Access**, choose the channel, and enter that code. This is separate from browser approval.

### Step 5: Start Chatting

1. Click **New conversation** in the OpenClaw sidebar
2. Type your first message
3. Enjoy your self-hosted AI assistant! 🎉

### Upgrading an Existing Installation

This branch pins **OpenClaw 2026.10.4** in `package.json`. Railway version variables, including an existing `OPENCLAW_VERSION`, are ignored. Keep your existing persistent volume mounted at `/data` when redeploying. The template migrates existing configuration and state during startup; allow the health check to complete before opening the UI.

Existing users do not need to run setup again. Use `/setup` → **Open OpenClaw UI** after the upgrade. Existing browser approvals are retained; a new browser or an import into another deployment may require pairing. Use **Export Data** first if you want a manual backup. **Reset configuration** and **Wipe all data** are not steps in an ordinary upgrade.

To change OpenClaw versions, select the corresponding release branch in Railway. Downgrading an already-migrated installation also requires a compatible pre-upgrade data backup; selecting an older branch does not reverse database changes. That backup will not include subsequent chats or edits.

---


## About Hosting OpenClaw Railway Template

Hosting OpenClaw involves running it as a long-lived service with access to environment variables, compute resources, and optional external APIs. This Railway template packages OpenClaw in a containerized service, handles startup configuration, and exposes it over Railway’s infrastructure. You deploy it with a few clicks, configure required environment variables, and interact with OpenClaw remotely via supported clients or SSH. No manual server setup or VM management required. 🚀

## Common Use Cases

* Running a self-hosted AI agent for task automation
* Experimenting with autonomous agents and workflows
* Hosting OpenClaw for development, testing, or internal tools

## Dependencies for OpenClaw Railway Template Hosting

* Railway account
* An API key or supported browser sign-in method for your chosen LLM provider

### Deployment Dependencies

- [OpenClaw GitHub Repository](https://github.com/openclaw/openclaw) - Source code for the AI agent framework
- [Anthropic API Keys](https://platform.claude.com/) - Claude AI models (recommended)
- [OpenAI API Keys](https://platform.openai.com/) - GPT models (alternative)
- [Google AI Studio](https://aistudio.google.com/) - Gemini models (alternative)
- [Telegram BotFather](https://t.me/botfather) - Create Telegram bots for messaging
- [Discord Developer Portal](https://discord.com/developers/applications) - Create Discord bots

---

## Frequently Asked Questions (FAQ)

### What is OpenClaw?

OpenClaw is a self-hosted AI agent framework that can execute commands, manage files, and perform automated tasks based on user instructions. It runs as a service and can be controlled remotely. 🤖

---

### What does this Railway template deploy?

This Railway template deploys OpenClaw as a containerized service on Railway with predefined startup and configuration support.

---

### Where can OpenClaw be deployed using this template?

Using this template, OpenClaw is deployed on Railway’s infrastructure and can be accessed remotely from your local machine or supported clients. ☁️

---

### How to deploy OpenClaw on Railway?

Click **Deploy on Railway**, follow the on screen simple steps and click on Run Setup. Once running, use the service URL or Railway SSH to interact with OpenClaw. 🚀

---

### Does this template deploy OpenClaw locally?

No.
This template deploys OpenClaw on Railway, not on your local machine.

---

### What environment variables are required to run OpenClaw?

Set `SETUP_PASSWORD` to protect the setup wizard and keep the persistent volume mounted at `/data`. Choose your provider in the wizard and supply an API key or complete a supported browser sign-in. To enable the terminal UI, set `ENABLE_WEB_TUI=true`.

---

### Can OpenClaw be accessed publicly when deployed on Railway?

Yes, depending on Railway settings (using SETUP_PASSWORD). You should restrict access if OpenClaw is running with sensitive permissions. 🔒

---

### Does this template include OpenClaw plugins or skills?

The template installs the plugins required by the provider and channels you select during setup. Manage additional plugins and skills from the OpenClaw UI.

---

### Is data persisted when OpenClaw is hosted on Railway?

Yes, because this template comes with a volume which is persisted across deployments.

---



## Why Deploy OpenClaw Railway Template on Railway?


Railway is a singular platform to deploy your infrastructure stack. Railway will host your infrastructure so you don't have to deal with configuration, while allowing you to vertically and horizontally scale it.

By deploying OpenClaw Railway Template on Railway, you are one step closer to supporting a complete full-stack application with minimal burden. Host your servers, databases, AI agents, and more on Railway.
