# KonQuest Meta Ads MCP

[![PyPI](https://img.shields.io/pypi/v/konquest-meta-ads-mcp)](https://pypi.org/project/konquest-meta-ads-mcp/) [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE) [![konquest-meta-ads-mcp MCP server](https://glama.ai/mcp/servers/brandu-mos/konquest-meta-ads-mcp/badges/score.svg)](https://glama.ai/mcp/servers/brandu-mos/konquest-meta-ads-mcp)

Supervised Meta Ads Operating System for Claude Code.

```bash
pip install konquest-meta-ads-mcp
```

## Open-Core Model

KonQuest Meta Ads MCP uses an open-core model.

**Public package, this repository, 57 tools, MIT license**
- Full CRUD for campaigns, ad sets, and ads
- Multi-asset ad creation for video and static image formats
- Image upload and retrieval
- Campaign duplication and standalone ad set duplication
- Single-account insights and bulk cross-account analytics
- Pixel and tracking diagnostics
- Catalog and DPA support, including product set create and update
- Full targeting toolkit
- Setup readiness checker with 42+ checks and fix instructions
- Validation pipeline, naming enforcement, post-write verification
- Safety tiers, rate limiting, rollback references
- 181 automated tests

**Premium bundle, adds 41 tools**
- Advisory optimization engine, review queues, learning, experiments, budget governor, creative rotation
- Vault intelligence and copy generation, including brand voice, ICP targeting, concept selection
- Greek language QA, Greeklish detection, orthography checks
- Automation suite, diagnostics, bulk operations, account audit
- Vault bootstrap, 15 template files per client
- Premium tests and evaluations

**[Get the Premium Bundle (€149 launch price)](https://farasokster.gumroad.com/l/konquest-meta-ads-mcp-premium)**  
One-time purchase, perpetual license. Public tools work fully without it.

## Quick Start

### 1. Install

```bash
pip install konquest-meta-ads-mcp
```

### 2. Copy environment template

```bash
cp .env.example .env
```

### 3. Set your token

Required:
- `META_ACCESS_TOKEN`

Optional:
- `META_APP_SECRET`
- `META_APP_ID`
- `VAULT_PATH`

### 4. Add it to Claude Code

Add this to your `.mcp.json`:

```json
{
  "mcpServers": {
    "meta-ads": {
      "command": "uv",
      "args": ["--directory", "/path/to/konquest-meta-ads-mcp", "run", "python", "-m", "meta_ads_mcp"],
      "env": {
        "META_ACCESS_TOKEN": "your_token_here",
        "VAULT_PATH": "/path/to/your/marketing-vault"
      }
    }
  }
}
```

### 5. Run setup validation

Use `run_setup_check` first to validate token, permissions, accounts, pages, IG, pixels, and vault readiness.

## What Makes This Different

- **Production-tested** across real client campaigns, real budgets, and real edge cases
- **Not a thin wrapper** around a handful of Meta API calls
- **Safety-first by design**, with validation, naming gates, diagnostics, verification, and rollback
- **Multi-asset workflows included**, for both video and static image variants
- **Supervised, not autonomous**, the operator confirms every meaningful write
- **Vault-aware architecture**, premium workflows can read client intelligence such as ICPs, brand voice, and messaging angles
- **Greek language QA built in**, adaptable to broader language validation workflows
- **Ads created paused by default**, nothing goes live without explicit operator intent

## Public Package Capabilities

The public repository contains the execution and control layer.

### Account management
- Token health
- Ad account discovery
- Pages
- Instagram identities
- Discovery workflows

### Campaigns
- Create
- Read
- Update
- Structural delete workflows

### Ad sets
- Create
- Read
- Update
- Standalone duplication

### Ads
- Create
- Read
- Update
- Creative swap workflows

### Creative workflows
- Standalone single-image creative creation
- Creative name update
- Multi-asset video workflows
- Multi-asset static image workflows

### Images and video
- Image upload from URL
- Image retrieval by hash
- Video upload
- Video processing status

### Insights and diagnostics
- Single-account insights
- Bulk cross-account insights
- Pixel diagnostics
- Tracking checks
- Catalog and DPA diagnostics

### Catalog and DPA
- Catalog reads
- Feed visibility
- Product set create
- Product set update

### Targeting
- Interests
- Behaviors
- Geo
- Demographics
- Suggestions
- Audience size estimation

### Setup and control
- Setup readiness checker
- Validation pipeline
- Naming enforcement
- Post-write verification
- Safety tiers
- Rate limiting
- Rollback references

## Premium Bundle Capabilities

The premium bundle adds the intelligence and optimization layer.

### Advisory Optimization Engine
- Optimization cycles
- Review queues
- Outcome evaluation
- Learning cycles
- Experiment planning and evaluation
- Budget governor
- Creative rotation
- Operator digests

### Vault Intelligence and Copy Generation
- Vault-driven copy generation
- Copy validation
- Brand voice grounding
- ICP-aware messaging
- Concept selection

### Automation Suite
- Greek language QA
- Full account diagnostics
- Bulk ad copy fixes
- Product extension workflows
- Multi-account audit

### Vault Bootstrap
- Creates 15 canonical template files per client
- Speeds up onboarding for premium intelligence workflows

## Tool Availability Summary

### Public package

| Category | Tools | Availability |
|----------|:-----:|-------------|
| Account Management | 6 | Public |
| Campaigns | 4 | Public |
| Ad Sets | 4 | Public |
| Ads | 4 | Public |
| Creatives | 3 | Public |
| Insights & Analytics | 2 | Public |
| Pixels & Tracking | 5 | Public |
| Catalogs & DPA | 6 | Public |
| Audiences | 1 | Public |
| Targeting | 6 | Public |
| Images | 2 | Public |
| Video Management | 2 | Public |
| Ad Builder | 1 | Public |
| Naming Convention | 1 | Public |
| Ops | 5 | Public |
| Vault Reader | 1 | Public |
| Duplication | 2 | Public |
| Setup | 1 | Public |

### Premium bundle

| Category | Tools | Availability |
|----------|:-----:|-------------|
| Automation & Diagnostics | 6 | Premium |
| Copy Engine | 2 | Premium |
| Vault Bootstrap | 1 | Premium |
| Advisory Optimization Engine | 32 | Premium |

## Full System Classification

This classification refers to the **full KonQuest system**, meaning public package plus premium bundle.

| Classification | Count | Description |
|----------------|:-----:|-------------|
| production-safe | 38 | Read-oriented access and low-risk operations |
| supervised-only | 29 | Write or change operations requiring operator approval |
| advisory-only | 31 | Recommendations, plans, diagnostics, copy, and local intelligence workflows |
| **Total** | **98** | Full system |

## Architecture

### Public package architecture

```text
meta_ads_mcp/
  core/          # Public API read/write modules
  safety/        # Rate limiting, rollback, tiers, duplicate checks
  validators/    # Compliance, creative, tracking, structure, operational validation
  engine/        # Public helper modules required by the open-core package
```

### Full platform architecture, public plus premium

```text
meta_ads_mcp/
  core/          # 66 tools across public and premium core workflows
  engine/        # 32 premium advisory and optimization tools
  validators/    # Quality gates
  safety/        # Rate limiting, rollback, duplicate checking, file locks, tier access
  ingestion/     # Internal ingestion and manifest pipeline
```

## Engine Features

- **Optimization loops** for budget shifting based on performance signals
- **Experiment management** with evaluation and winner promotion workflows
- **Budget governors** to reduce overspend risk
- **Creative rotation** to detect fatigue and stale creative conditions
- **Policy learning** to track outcomes and adapt confidence over time
- **Naming gate** to enforce consistent naming before API writes

## Safety Features

- **Rate limiting** with backoff for Meta API usage
- **Rollback** for recent changes with execution journal support
- **Duplicate checking** to reduce accidental duplicate campaign and ad creation
- **File locks** for safer concurrent local state access
- **Tier-based access** with sandbox, standard, and production-style controls

## Validator Suite

- **Compliance validator** for policy-oriented pre-checks
- **Creative spec validator** for image and video validation
- **Tracking validator** for pixel and event verification
- **Structure validator** for campaign structure consistency
- **Operational validator** for budget, schedule, and targeting sanity checks

## Setup

### 1. Install

```bash
pip install konquest-meta-ads-mcp
```

Or from source:

```bash
git clone https://github.com/brandu-mos/konquest-meta-ads-mcp.git
cd konquest-meta-ads-mcp
uv sync
```

### 2. Environment Variables

Copy `.env.example` to `.env` and fill in your values:

```bash
cp .env.example .env
```

Required:
- `META_ACCESS_TOKEN`, Meta Marketing API access token, system user token recommended

Optional:
- `META_APP_SECRET`, for `appsecret_proof`, recommended for production
- `META_APP_ID`, Meta app ID
- `VAULT_PATH`, path to your marketing vault directory, defaults to `~/marketing-vault`

### 3. MCP Configuration

Add to your Claude Code MCP config (`.mcp.json`):

```json
{
  "mcpServers": {
    "meta-ads": {
      "command": "uv",
      "args": ["--directory", "/path/to/konquest-meta-ads-mcp", "run", "python", "-m", "meta_ads_mcp"],
      "env": {
        "META_ACCESS_TOKEN": "your_token_here",
        "VAULT_PATH": "/path/to/your/marketing-vault"
      }
    }
  }
}
```

### 4. Vault Usage

Vault usage is **optional for the public open-core package**.

Premium intelligence and copy workflows rely on vault-based client context.

If using vault-backed workflows:

```text
your-vault/
  01_CLIENTS/{client-slug}/
    00-profile.md
    02-icp-personas.md
    04-brand-voice.md
    05-messaging-house.md
    08-objections.md
    matrix.md
  02_COMPETITORS/{slug}/
    landscape.md
```

## Testing

```bash
uv run --extra dev python -m pytest tests/ -v
```

- **Public package:** 181 passing
- **Full system with premium:** 246 passing

## Premium Bundle

The premium bundle upgrades the public package into the full KonQuest system.

It adds 41 tools for:

- Advisory optimization engine
- Vault intelligence
- Copy generation
- Greek language QA
- Automation workflows
- Vault bootstrap
- Premium tests and evaluations

**[Get the Premium Bundle (€149 launch price)](https://farasokster.gumroad.com/l/konquest-meta-ads-mcp-premium)**

### Commercial model
- One-time purchase
- Perpetual license for the purchased version
- No subscription
- No redistribution or resale

## Who This Is For

KonQuest is a fit for:
- Meta Ads operators
- Agencies
- Solo performance marketers
- Technical marketers working in Claude Code
- Builders who want a supervised Meta Ads operating layer

## Who This Is Not For

KonQuest is not a fit for:
- People who want a hosted SaaS dashboard
- Users looking for autonomous ad buying
- Buyers who want a no-setup web app
- People who do not work with Meta Ads operations

## License

MIT, see [LICENSE](LICENSE).

<!-- mcp-name: io.github.brandu-mos/konquest-meta-ads-mcp -->
