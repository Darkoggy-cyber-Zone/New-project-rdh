MH MUBASSIR AI AGENT V2 — TERMUX
Developer: MH Mubassir

FEATURES
- Premium responsive chat UI, theme toggle, new chat, local chat history
- Gemini API chat with bilingual/empathy-focused system instructions
- Web search (DuckDuckGo)
- Explicit memory saved locally
- AI generated files saved only from ```file:relative/path blocks into workspace/
- Command center with a short allowlist of read-only/safe commands and user confirmation
- Browser voice input/output where supported

INSTALL IN TERMUX
pkg update && pkg upgrade -y
pkg install python python-pip -y
cd ~/mh-mubassir-ai-agent-v2
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
nano .env
# Paste your key after GEMINI_API_KEY=, save Ctrl+O, Enter, Ctrl+X
python app.py

Open on the same phone:
http://127.0.0.1:5000

COMMAND CENTER SECURITY
- This starter does NOT provide arbitrary shell access.
- Only listed commands (pwd, ls, python --version, pip --version, workspace file listing) can run.
- Command runs in project/workspace context with timeout and output limit.
- No rm, chmod, curl, package installation, arbitrary scripts, or root commands.
- AI-generated code is saved, never automatically executed.
- For more commands, add an explicit allowlist entry and review the security implications first.

API SECURITY
- Keep .env private; never paste your API key into chat or frontend code.
- Server binds to 127.0.0.1 by default.
- Do not expose this development server to the internet.
- Gemini API usage quotas/pricing depend on your account.
- The assistant can respond empathetically but does not literally feel human emotions.
- Browser voice recognition/TTS depends on browser, Android speech services and permissions.
