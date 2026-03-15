<p align="center">
  <img src="https://raw.githubusercontent.com/opensoar-hq/opensoar-www/main/public/logo.svg" width="64" height="64" alt="OpenSOAR">
</p>

<h1 align="center">OpenSOAR</h1>
<p align="center"><strong>Open-source Security Orchestration, Automation & Response</strong></p>

<p align="center">

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Website](https://img.shields.io/badge/website-opensoar.app-purple)](https://opensoar.app)

</p>

A Python-native SOAR platform with built-in AI. Write playbooks in real Python — not YAML, not drag-and-drop. AI-powered triage, playbook generation, and alert correlation included free and open-source.

```python
@playbook(trigger="alert.created", conditions={"severity": "critical"})
async def triage_critical(alert):
    results = await asyncio.gather(
        virustotal.lookup(alert.iocs),
        abuseipdb.check(alert.source_ip),
    )
    if any(r.malicious for r in results):
        await pagerduty.create_incident(alert)
```

## Repos

| Repo | Description |
|------|-------------|
| [`opensoar-core`](https://github.com/opensoar-hq/opensoar-core) | Core platform — API, UI, worker, playbook engine, AI triage |
| [`opensoar-sdk`](https://github.com/opensoar-hq/opensoar-sdk) | Python SDK for integration & playbook authors |
| [`opensoar-integrations`](https://github.com/opensoar-hq/opensoar-integrations) | Community integration packs (CrowdStrike, SentinelOne, Jira, etc.) |
| [`opensoar-deploy`](https://github.com/opensoar-hq/opensoar-deploy) | Docker Compose configs for deployment |
| [`opensoar-www`](https://github.com/opensoar-hq/opensoar-www) | Landing page — [opensoar.app](https://opensoar.app) |

## Getting Started

```bash
curl -fsSL https://opensoar.app/install.sh | sh
```

## Links

[Website](https://opensoar.app) · [Apache 2.0 License](https://opensource.org/licenses/Apache-2.0)
