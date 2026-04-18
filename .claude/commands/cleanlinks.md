# /cleanlinks — Vault Link Audit

Perform a full audit of unresolved WikiLinks (stubs) across the Korlornium vault at `C:\Users\austi\Documents\Korlornium`.

## What to do

Use the `obsidian-vault-curator` subagent to scan all `.md` files and identify every unresolved WikiLink. Categorize them into three buckets and present the results to the user before making any changes.

### Bucket 1 — Needs Rename
Links that point to real existing articles but use the wrong form:
- Path-style links like `[[Folder/Article]]` — Obsidian resolves by filename, path is wrong
- Typos (e.g. `[[Frostcrag Glave]]` instead of `[[Frostcrag Glade]]`)
- Missing "The" prefix or other name mismatches

### Bucket 2 — Keep as Stub
Legitimate unwritten articles that deserve their own note per the vault's article rules:
- All named people and places
- Named unique items, factions, creatures, and world-specific concepts

### Bucket 3 — Should Be Removed
Links that don't warrant articles:
- Mundane real-world items (a hammer, generic food with no cultural significance)
- Standalone year/date references (use a History article instead)
- Generic D&D species with no Erodas-specific lore
- Meta-vault references that aren't real articles

## Article rules (from CLAUDE.md)
- People and places always get their own article
- Things get an article only if unique to Erodas, relevant to a story or history, or of cultural importance
- Dates don't get standalone articles — write a History/Event article if historically significant
- Article names must be unique; disambiguate with parentheses: e.g. `Dithoria City` vs `Dithoria (God)`

## Naming rules
- Character names must be written in full: `[[Yannis Trask]]` not `[[Yannis]]`
- Shortened display names use aliases: `[[Yannis Trask|Yannis]]`
- Cultural/demonym references use aliases: `[[Dithoria City|Dithorian]]` not a stub called `Dithorian`

## Output format
Present findings as three labelled tables. For **Bucket 1**, include the bad link, the correct link, and the files affected. For **Bucket 3**, include the link and files. Ask the user to approve before making any changes.

After approval, apply all fixes: rename links in-place using `sed` across affected files, and remove brackets from links that should be plain text.
