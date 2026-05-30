# 🪤 LLM Honeypot

> A proactive honeypot for detecting and trapping Prompt Injection, Jailbreak, and other LLM-based attacks.

As LLMs become widely integrated into enterprise systems, attackers are actively developing new methods to exploit them. Defensive tools remain critically scarce. This project aims to fill that gap.

## 🎯 What It Does

A web service disguised as a corporate AI assistant, but actually a trap for malicious actors:

- 🔍 **Detects** Prompt Injection, Jailbreak, and system prompt leakage attempts
- 🎭 **Deceives** the attacker by returning realistic but fake "secret data"
- 📝 **Logs** every attack with full context for threat intelligence

## 🧠 How It Works

1. Accepts user prompts via REST API or built-in chat interface
2. Classifier (heuristic → DistilBERT) inspects the prompt for malicious intent
3. If an attack is detected — returns convincing fake credentials and tokens
4. Logs the attacker's IP, prompt, matched patterns, and timestamp

## 🚀 Quick Start

```bash
# Clone the repo
git clone https://github.com/romiisromie/llm-honeypot.git
cd llm-honeypot

# Install dependencies
pip install fastapi uvicorn

# Run the server
uvicorn main:app --reload
