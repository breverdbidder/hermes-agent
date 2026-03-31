# Hermes-Agent Fork: Adoption Plan

## What We're Taking

From NousResearch/hermes-agent v0.6.0 (MIT, 9.8k stars):

### 1. RL Trajectory Engine (PRIORITY #1 — THE MOAT)
- `environments/agent_loop.py` — multi-turn agent loop with trajectory recording
- `environments/hermes_base_env.py` — base environment with reward scoring
- `trajectory_compressor.py` — compress trajectories for training efficiency
- `tinker-atropos/` — RL training integration

**Adapted for:** Shapira Formula self-improvement. Every auction prediction → trajectory → outcome → reward score → monthly retrain → formula adapts per zip/auction_type.

### 2. Multi-Channel Gateway (PRIORITY #2 — CLIENT ACQUISITION)
- `gateway/run.py` — single-process multi-platform dispatcher
- `gateway/session.py` — cross-platform session continuity
- `gateway/platforms/telegram.py` — reference adapter (we know Telegram)
- `gateway/platforms/whatsapp.py` — WhatsApp adapter
- `gateway/platforms/email.py` — Email adapter
- `gateway/platforms/sms.py` — SMS adapter

**Adapted for:** ZoneWise.AI + BidDeed.AI client channels through Dify backend.

### 3. Self-Improving Skills Loop (PRIORITY #3 — AGENT INTELLIGENCE)
- `run_agent.py` lines 1539-1670 — background review spawns agent fork
- `tools/skill_manager_tool.py` — autonomous skill creation/editing
- `tools/skills_guard.py` — security scanning for skills

**Adapted for:** cli-anything-biddeed skills that improve from experience.

### 4. Memory Security Patterns (PRIORITY #4 — RAG SAFETY)  
- `tools/memory_tool.py` — injection/exfiltration scanning patterns
- `tools/tirith_security.py` — pre-execution security scanning

**Adapted for:** Obsidian vault + ZoneWise RAG pipeline safety.

## Fork Setup

```bash
# After forking via GitHub UI:
git clone https://github.com/breverdbidder/hermes-agent.git
cd hermes-agent

# Add upstream for syncing updates
git remote add upstream https://github.com/NousResearch/hermes-agent.git

# Create our customization branch
git checkout -b everest-adaptations

# Extract just what we need into our ecosystem repos
```

## Files to Extract → Ecosystem Repos

| Source File | Destination Repo | Purpose |
|------------|-----------------|---------|
| `environments/*.py` | `brevard-bidder-scraper` | RL reward engine for XGBoost |
| `trajectory_compressor.py` | `brevard-bidder-scraper` | Trajectory compression |
| `gateway/run.py` | `zonewise-web` (new `/gateway`) | Multi-channel client gateway |
| `gateway/platforms/*.py` | `zonewise-web` | Platform adapters |
| `gateway/session.py` | `zonewise-web` | Session management |
| `tools/skill_manager_tool.py` | `cli-anything-biddeed` | Self-improving skills |
| `tools/skills_guard.py` | `cli-anything-biddeed` | Skill security |
| `tools/memory_tool.py` (patterns) | `everest-vault` | RAG injection scanning |
