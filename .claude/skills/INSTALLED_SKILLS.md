# Installed SEO skill packs

| # | Pack | Source | Entry skill(s) |
|---|------|--------|----------------|
| 01 | claude-seo | https://github.com/AgriciDaniel/claude-seo | `seo`, `seo-*` (+ `seo-*` agents) |
| 02 | geo-seo-claude | https://github.com/zubair-trabzada/geo-seo-claude | `geo`, `geo-*` (+ `geo-*` agents) |
| 03 | schema | https://github.com/coreyhaines31/marketingskills (skills/schema) | `schema` |
| 04 | programmatic-seo | https://github.com/coreyhaines31/marketingskills (skills/programmatic-seo) | `programmatic-seo` |
| 05 | claude-blog | https://github.com/AgriciDaniel/claude-blog | `blog`, `blog-*` (+ blog agents) |

Installed as project skills by copying files (installers were not run).
Plugin-root / `~/.claude/skills` paths were rewritten to `${CLAUDE_PROJECT_DIR}/.claude/skills/`.
Optional Python helpers need their deps: `pip install -r .claude/skills/{seo,geo,blog}/requirements.txt`.
claude-seo's PostToolUse schema-validation hook was not enabled.
All are MIT-licensed; see each upstream repo for LICENSE.
