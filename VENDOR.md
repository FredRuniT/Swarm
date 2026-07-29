# Vendored: Swarm

| Field | Value |
|-------|-------|
| Upstream | https://github.com/christopherkarani/Swarm |
| Pinned SHA | `3ee2670761d979992d0e8b381030f1d9fb0cbc2a` |
| Upstream date | 2026-07-17 |
| Vendored into | RuniT-Chat |
| License | See `LICENSE` (MIT) |

## Local edits

- `Package.swift`: Conduit dependency uses `https://github.com/FredRuniT/Conduit.git` exact `0.6.0-runit` (not upstream; swift-syntax ..<604).
- Conduit traits enabled: OpenAI, OpenRouter, Anthropic (MLX trait deferred — Cmlx under parent SPM graph).
- `swift-syntax` range widened to `"600.0.0"..<"604.0.0"` for SkillSets / mlx-swift-lm 603.x.
- Conduit MLX provider sources gated with `CONDUIT_TRAIT_MLX && canImport(MLX)` (was `canImport(MLX)` only). SkillSets already imports MLX via FoundationChatKitMLX, so the old guard compiled Swarm MLX bridges against a Conduit build without the MLX trait.

Published mirror for remote consumers: tag `0.7.0-runit` on `https://github.com/FredRuniT/Swarm.git`.

## Docs

Keep `docs/` as the upstream API reference. RuniT index: `../../docs/PRD_SWARM_RUNIT_CHAT.md`.
