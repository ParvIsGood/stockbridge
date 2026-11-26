# PROGRESS.md: the hand-off log

Newest entry at the top. Every session, by any person or any agent, adds one entry before it stops. This file is how a fresh session on another account picks up with zero context.

## Template (copy this)

```
## YYYY-MM-DD HH:MM · p<NN> <prompt name> · <who> (<tool / account>)
**Branch / PR:** p<NN>-slug · #PR
**Done:** what now works (link files, screenshots in docs/screens/)
**Not done / next step:** the exact next action, so the next session can start immediately
**Decisions:** anything new (also add to docs/DECISIONS.md)
**Gates:** backend tests ✓/✗ · android build ✓/✗ · web build ✓/✗ · reviewed by codex/agy ✓/✗
**Blockers / questions for Daivik:**
```

---

## 2026-11-26 · p04 market research · Parv (Claude)
**Branch / PR:** p04-market-research
**Done:** `docs/research/MARKET.md`: one deep-research report (`docs/research/raw/research_brief.md`) fact-checked source by source. Contents: 10 deck numbers with labels, competitor table, rebuilt market size (₹702 Cr India / ~₹15 Cr Punjab, shop-capped), ROI check at ₹150/shop/month, and a corrections log. Major fixes: VoiceKhata is now free; Punjab counts cut to the 2.19% population share; the inflated ₹3,645 Cr figure moved to the appendix.
**Not done / next step:** a second deep-research report was not run (optional). Replace the vendor-only expiry numbers with real distributor answers from interviews (05).
**Decisions:** price ₹150/active shop/month throughout. Flag for Daivik: at that price ROI only works for distributors above ~₹10 Cr turnover. Consider outcome-based pricing, or brands as a second payer.
**Gates:** docs only.
**Blockers / questions for Daivik:** are interviews (05) happening? MARKET.md section 10 lists the questions they need to answer.

## 2026-11-25 · playbook · Claude (lead session)
**Done:**
- Added the build playbook: `playbook/` (master workflow, criteria, tools setup, budget, prompts 00–34).
- Added the agent rules (`AGENTS.md`, `CLAUDE.md`), the committed MCP config (`.mcp.json`), helper scripts (`scripts/`) and the `second-opinion` skill.

The code is unchanged: the Python agent still runs from the root, as in the README.

**Next step:** everyone runs `playbook/prompts/00_setup.md`. Then Daivik runs `01_plan_master.md`.
**Decisions:** stack fixed as in AGENTS.md section 4 (native Kotlin + Compose, Next.js, FastAPI); online-first with an outbox.
**Gates:** backend tests ✓ (15 passed).
