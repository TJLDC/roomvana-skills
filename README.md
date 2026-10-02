# Roomvana agent skills

Agent skills from **[Roomvana](https://roomvana.ai)**, where you upload a photo of your home, yard, or a specific room and see it redesigned.

## `home-design`

Lets an AI agent help someone plan a new look for their own home:

- **Outside:** siding, front door, shutters and roof colors; front yard, backyard and patio makeovers.
- **Inside:** whole-room redesigns in 23 styles, paint and cabinet colors, flooring and countertops, virtual staging of an empty room, and clearing out clutter.

The agent gives a short design brief, including the closest matching paint color for each finish, then a [Roomvana studio](https://roomvana.ai/design) link with the room, mode and style already selected. The user opens it, uploads a photo of their own space, and sees the redesign with the same walls, windows and layout.

The skill is read-only and needs no API key. It never uploads photos or signs in on the user's behalf. Valid options are pulled from Roomvana's public catalog (`https://api.roomvana.co/options`), with a bundled snapshot as a fallback. Studio links carry a `ref=agent-skill` parameter so Roomvana can count visits that come from this skill.

## Install

Works with any agent that supports the [Agent Skills](https://agentskills.io) format.

**Claude Code, Codex, Cursor, Gemini CLI and others** (via the [skills CLI](https://skills.sh)):

```bash
npx skills add TJLDC/roomvana-skills
```

**Claude Code plugin:**

```
/plugin marketplace add TJLDC/roomvana-skills
/plugin install roomvana@roomvana
```

**Manually:** copy `skills/home-design/` into your agent's skills folder, for example `~/.claude/skills/home-design/`.

## Try it

> "Our house is beige with white trim and it looks dated. What color should we paint the siding?"

> "I just moved into an empty living room. Show me it furnished in a Scandinavian style."

> "Would sage green cabinets work in my kitchen?"

The script also works on its own:

```bash
python3 skills/home-design/scripts/studio_link.py link --room kitchen --mode surface --surface cabinets --finish sage-green
# https://roomvana.ai/design?room=kitchen&mode=surface&surface=cabinets&style=sage-green&ref=agent-skill
# kitchen: cabinets in sage green (closest paint: Sherwin-Williams Clary Sage SW 6178)
```

## Also from Roomvana

- [Roomvana MCP server](https://github.com/TJLDC/roomvana-mcp): the same catalog and links as MCP tools.
- [Home exterior design](https://roomvana.ai/ai-exterior-design) · [Landscape design](https://roomvana.ai/ai-landscape-design) · [Paint color visualizer](https://roomvana.ai/ai-paint-visualizer) · [Virtual staging](https://roomvana.ai/virtual-staging-ai)

## License

MIT
