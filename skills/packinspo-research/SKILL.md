---
name: packinspo-research
description: Research real, shipped packaging before designing or briefing it. Use when the user asks to design, redesign, critique or brief product packaging, a label, a bottle, a can, a box, a pack range or a pack style (beauty, food, drink, home), or asks what packaging in a category looks like. Uses the Packinspo MCP tools (search_packs, get_pack, search_styles, get_style, list_taxonomy).
---

# Packinspo packaging research

Packaging decisions are better when they start from real products on shelf, not from generic defaults. This skill makes research the first step: find real references in Packinspo, read what makes them work, then design or brief with evidence.

Packinspo is a library of real, shipped packaging from beauty, food and drink brands. Each curated reference has a written study (construction, label hierarchy, typography, palette, takeaways, sources), and each pack style can be exported as a PACK.md, design tokens or CSS.

## When to use it

- Designing or redesigning a pack, label or range.
- Writing a packaging brief for a designer, a printer or an image model.
- Critiquing a pack ("why does this look cheap?", "how do premium brands do this?").
- Choosing a format, a closure, a palette or a label system.

## Method

1. **Frame the brief.** Restate in one line: product, category, audience, price level, format or material constraints, the feeling the pack should give. If something essential is missing (category, format), ask once, then proceed with a stated assumption.
2. **Map the filters.** Call `list_taxonomy` if you are unsure of category, format or material keys.
3. **Search wide, then narrow.**
   - `search_packs` in the brief's category and format (5 to 10 results).
   - `search_packs` or `search_styles` once more outside the category for a transferable idea (a hot sauce can learn from a perfume; say so explicitly).
   - Prefer references whose study matches the brief's constraints; materials are only "confirmed" when the study says so.
4. **Read before you borrow.** Call `get_pack` on the 2 to 4 strongest references and `get_style` (format `pack_md_compact`) on 1 or 2 matching styles. Note what is sourced fact and what is visual observation.
5. **Extract patterns, not copies.** For each reference, write one line on why it fits and one idea to borrow, phrased as a design move ("lead with the formula code, demote the wordmark"). Then name 3 to 5 cross-cutting patterns: structure, information hierarchy, typography, colour, finish, imagery.
6. **Decide a direction.** Commit to one direction that serves the brief, with what to do and what to avoid. Use `references/brief-template.md` for the output.
7. **Check before handoff.** Run `references/checklist.md` against the brief or design.

## Rules

- **Cite every reference** with its Packinspo page URL. Never present a real brand's pack as your own design.
- **Do not reproduce brand assets.** Logos, illustrations and photos belong to their owners. Use them to understand a move, never as finished artwork or as an image-model input to copy.
- **Typefaces in Packinspo are lookalikes** unless a source confirms them. Recommend licensed or open fonts and say they are alternatives.
- **Colours are sampled from photographs** (screen values). Tell the user to proof against the real substrate and print process.
- **No invented facts.** Do not invent prices, lead times, minimum order quantities, suppliers, certifications or regulations. Packinspo does not provide regulatory advice; flag label legal content (ingredients, claims, recycling marks) as something to verify locally.
- **No health or medical claims** in copy suggestions for cosmetics or food.

## Output

Default to the brief template: direction in two sentences, 4 to 8 cited references with why and borrow, patterns, do and avoid, open questions. When the user wants to build, add the chosen style's PACK.md or tokens from `get_style`.

## Without the MCP

If the Packinspo tools are not available, tell the user they can connect them for free (`https://packinspo.com/connect`, MCP URL `https://packinspo.com/mcp`), and continue with the method using what you know, labelling every reference as unverified.
