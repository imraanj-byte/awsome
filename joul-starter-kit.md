# Joul AI Call Answering - Claude Code Starter Kit

A curated selection of Claude Code resources specifically for **AI-powered missed call automation** services.

## Overview

This kit brings together the best tools, skills, and patterns from the Awesome Claude Code community for building intelligent call handling systems.

---

## 🎯 Core Resources by Category

### Voice & Call Handling
- **[dictate](https://github.com/vimalk78/dictate)** - Local, offline voice-to-text transcription with faster-whisper. Fully private, no cloud/APIs needed. Perfect for processing voicemail and call recordings offline.
- **[Happy Coder](https://github.com/slopus/happy)** - Control Claude Code from phone/desktop with real-time voice. Useful for remote agent management and voice-enabled approvals.

### Notifications & Alerts
- **[ai-agent-notifier](https://github.com/DevinoSolutions/ai-agent-notifier)** - Zero-dependency push notifications (desktop toast + phone push via ntfy). Critical for alerting you when a call comes in or needs intervention.
- **[Claude Threads](https://github.com/anneschuth/claude-threads)** - Stream agent sessions live into Slack/Mattermost threads. Great for team visibility of incoming calls.

### Agent Orchestration & Coordination
- **[Agent Collab Skills](https://github.com/WenyuChiou/agent-collab-skills)** - Multi-agent collaboration: task splitter, output reconciler, shared memory, acceptance gates. Essential for handling complex call scenarios.
- **[AgentSys](https://github.com/avifenesh/agentsys)** - Complete workflow automation with agents, skills, plugins. Mature, production-tested, great for orchestrating call workflows.

### Memory & Context Persistence
- **[Claude Mnemonic](https://github.com/lukaszraczylo/claude-mnemonic)** - Memory management for Claude Code. Critical for remembering caller history, previous interactions, and context across calls.

### Observability & Monitoring
- **[Claude Code Agent Monitor](https://github.com/hoangsonww/Claude-Code-Agent-Monitor)** - Real-time dashboard monitoring agent activity via hooks. Track call processing, agent status, tool usage.
- **[AgentWatch](https://github.com/mishanefedov/agentwatch)** - Local observability for AI agents. Monitor what's happening in real-time.
- **[Claude Code Observability Stack](https://github.com/ColeMurray/claude-code-otel)** - OpenTelemetry + Grafana stack for tracking performance, tokens, costs.

### Integration & Remote Control
- **[CloudCLI (Claude Code UI)](https://github.com/siteboon/claudecodeui)** - Web/mobile PWA to control Claude Code from any device. Great for managing agents remotely.
- **[Telegram-Claude (tg-claude)](https://github.com/Imolatte/tg-claude)** - Control Claude Code via Telegram bot. Voice input, git panel, Mac remote control, 30+ commands.
- **[WhatsApp Channel Plugin](https://github.com/Rich627/whatsapp-claude-plugin)** - Native WhatsApp integration via Baileys. Bidirectional messaging, voice transcription, media support.

---

## 📚 Learning & Architecture

### Foundational Patterns
- **[Building Effective Agents](https://www.anthropic.com/research/building-effective-agents)** - Anthropic's taxonomy: prompt chaining, routing, orchestrator-workers, evaluator-optimizer. Start here.
- **[Agent Skills](https://github.com/anthropics/skills)** - Official SKILL.md format and templates from Anthropic.
- **[How We Built Our Multi-Agent Research System](https://www.anthropic.com/engineering/multi-agent-research-system)** - Multi-agent coordination patterns that apply directly to call handling.

### Best Practices
- **[Effective Context Engineering for AI Agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)** - Curating context windows: compaction, JIT retrieval, note-taking. Critical for call summaries & history.
- **[Agentic Workflow Patterns](https://github.com/ThibautMelen/agentic-workflow-patterns)** - 190+ patterns with Mermaid diagrams and code examples.

---

## 🏗️ Recommended Setup

### Phase 1: Foundation
1. **Voice Processing** → Install `dictate` for offline transcription
2. **Memory** → Add `claude-mnemonic` for caller history
3. **Notifications** → Set up `ai-agent-notifier` for alerts

### Phase 2: Orchestration
1. **Agent Skills** → Use `agent-collab-skills` for multi-agent workflows
2. **Integration** → Add notification channels (Telegram, WhatsApp, Slack)
3. **Monitoring** → Deploy `claude-code-agent-monitor` for visibility

### Phase 3: Production
1. **Observability** → Full OpenTelemetry stack for tracking
2. **Remote Control** → CloudCLI or Telegram for team management
3. **Scaling** → AgentSys for complex workflow automation

---

## 💡 Integration Ideas

### Incoming Calls → AI Response
```
Phone Ring → Webhook Trigger → Claude Agent
    ↓
[Analyze voicemail/caller context]
    ↓
[Generate response (email, callback, forward)]
    ↓
[Log to memory + notify team]
    ↓
[Webhook response back to phone system]
```

### Team Collaboration
- Slack thread with `claude-threads` → Live agent visibility
- Push notifications via `ai-agent-notifier` → Team alerts
- WhatsApp integration → Direct team messaging
- Remote control via `tg-claude` → Pause/adjust agent behavior

### Quality Monitoring
- Observability stack tracks every call
- Memory system learns caller preferences
- Agent monitor shows real-time metrics
- Cost tracking via OpenTelemetry

---

## 🚀 Quick Start Template

```yaml
# .claude/settings.json additions
{
  "skills": [
    "github:vimalk78/dictate",           # Voice transcription
    "github:lukaszraczylo/claude-mnemonic",  # Memory
    "github:DevinoSolutions/ai-agent-notifier"  # Notifications
  ],
  "plugins": [
    "github:Rich627/whatsapp-claude-plugin",  # WhatsApp integration
    "github:Imolatte/tg-claude"  # Telegram control
  ],
  "hooks": {
    "on_session_start": "setup-joul-context",
    "on_tool_result": "log-call-event",
    "on_session_end": "save-call-summary"
  }
}
```

---

## 📖 Community Resources for Call Automation

- **[Claude Code: Everything You Need to Know](https://github.com/wesammustafa/Claude-Code-Everything-You-Need-to-Know)** - Conceptual primer on agentic loops
- **[Enterprise Skills](https://github.com/netresearch/claude-code-marketplace)** - Security, quality, automation patterns
- **[Encyclopedia of Agentic Coding Patterns](https://aipatternbook.com)** - 190+ patterns with solutions

---

## 🔗 Joul-Specific Next Steps

- [ ] Set up local voice transcription with `dictate`
- [ ] Implement call history memory with `claude-mnemonic`
- [ ] Create notification pipeline for incoming calls
- [ ] Build multi-agent coordinator for complex calls
- [ ] Deploy monitoring dashboard
- [ ] Integrate with your phone system API
- [ ] Set up team channels (Slack/WhatsApp/Telegram)
- [ ] Test end-to-end call handling flow

---

**Last updated:** 2026-10-03  
**Status:** Ready for implementation  
**Maintained by:** Joul AI Team
