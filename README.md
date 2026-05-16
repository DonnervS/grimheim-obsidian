# Grimheim — Obsidian Theme

A grim-dark fantasy tabletop theme for **Obsidian**. Built for **Grimheim** GM vaults: warbands, missions, factions, lore.

A full Obsidian theme — install it, pick it in Appearance. **Dark-only.**

---

## What's in this package

```
grimheim-obsidian/
├── theme.css                   ← the theme
├── manifest.json               ← theme manifest
├── fonts/
│   └── GrimheimGothic-Thin.otf
├── templates/                  ← five blank, reusable note templates
│   ├── Warband Overview.md
│   ├── Mission.md
│   ├── Faction.md
│   ├── Location.md
│   └── Session Log.md
├── examples/
│   └── Die Bleichgarde.md      ← a fully filled-in warband, for reference
├── assets/
│   └── grimheim-logo-dark.webp
└── README.md
```

---

## Install — three steps

### 1. Copy the theme into your vault

In your vault folder, find the hidden folder `.obsidian/themes/`
(create it if it doesn't exist). Make a folder named `Grimheim` inside it
and copy these in, keeping the structure:

```
.obsidian/themes/Grimheim/theme.css
.obsidian/themes/Grimheim/manifest.json
.obsidian/themes/Grimheim/fonts/GrimheimGothic-Thin.otf
```

`theme.css` expects the font at `fonts/GrimheimGothic-Thin.otf` relative to itself.

### 2. Select it in Obsidian

`Settings → Appearance → Themes → Grimheim`

Make sure base color scheme is set to **Dark**. (Restart Obsidian if the theme
doesn't appear in the dropdown.)

### 3. (Optional) Install the templates

Copy everything from `templates/` into a folder in your vault, e.g. `Templates/`. Then:

`Settings → Templates → Template folder location` → point it at that folder.

Insert a template into any note with the command **Templates: Insert template** (bind it to a hotkey if you use it often).

---

## Templates

Five blank, reusable note templates ship in `templates/`. Each is built for the **core Templates plugin** — it fills `{{title}}` from the note name and `{{date}}` from today's date on insert. Every template is wired to the theme's headings, tables, and custom callouts.

| Template | `type` | Use it for |
|---|---|---|
| `Warband Overview` | `warband` | A warband: roster, stash, vow, standing orders, injuries, campaign log, faction standings |
| `Mission` | `mission` | A single battle: briefing, deployment, objectives, forces, outcome, casualties, loot |
| `Faction` | `faction` | A power in the world: figures, holdings, relations, rumours, lore |
| `Location` | `location` | A place on the map: description, features, inhabitants, hazards, hooks, history |
| `Session Log` | `session` | One night at the table: recap, beats, notable rolls, casualties, gains, cliffhanger |

Workflow: create a note, name it (this becomes the `{{title}}` heading), then run **Templates: Insert template** and pick the matching type. Fill the placeholders — `0`, empty `[[ ]]` links, em-dashes — with your own content.

A fully worked example lives in `examples/Die Bleichgarde.md` — read it to see a finished warband before you write your own.

---

## Variants

The theme ships opt-in variants. Install the **Style Settings** plugin
(`Settings → Community plugins`) and they appear as toggles under
`Settings → Style Settings → Grimheim` — no CSS editing needed.

| Setting | Effect |
|---|---|
| *(defaults)* | Gothic display headings, iron-seal callouts |
| Blood-accent intensity | Slider `1`–`1.8` — strength of blood-red tag and accent tints |
| Fell English headings | H1/H2 swap to **IM Fell English SC** (less bold, more antiquarian) |
| Woodcut callout frame | Callouts get a double-stroke woodcut frame |
| Parchment callouts | Callouts render as parchment slips with iron-stamp header |
| Paper-grain overlay | Subtle paper-grain texture across notes |
| Illuminated drop-caps | First paragraph of every note gets an IM Fell English drop-cap |

Without Style Settings the theme still works — it just uses the defaults.
Advanced users can also set the underlying `body` classes (`gh-heading-fell`,
`gh-callout-woodcut`, `gh-callout-parchment`, `gh-grain`, `gh-dropcap`) by hand.

---

## Custom callouts

In addition to Obsidian's built-in `[!note]`, `[!warning]`, etc., this theme styles six Grimheim-specific callouts:

```markdown
> [!warband] Die Bleichgarde
> Roster and standing orders.

> [!faction] Order of the Lantern
> Bureaucratic, pedantic, slow to anger.

> [!mission] The Hollow Brunnen
> Night mission. 1200 pts. Recover the sigil.

> [!rule] Engagement
> Movement order: scouts first, captain last.

> [!dice] 2D6 + 1
> Result rendered in mono, gold-leaf color.

> [!vow] Standing Oath
> Rendered in IM Fell English italic, blood-edged.
```

---

## Iconography

The theme doesn't ship icons — Obsidian uses Lucide internally and that's left alone. Inside notes, prefer the dingbats:

`✠   ☠   †   ⚔   ⛓   ☾   ✦`

**No emoji.**

---

## Replacing / extending

- All tokens are prefixed `--gh-*` and defined at the top of `theme.css`. Override them in a CSS snippet to retint without editing the theme.
- The CSS targets both **Live Preview** (`.cm-header-*`, `.HyperMD-*`) and **Reading View** (`.markdown-preview-view`). Keep both updated if you edit headings.
- Body and accent faces (Vollkorn, IM Fell English, Manrope, JetBrains Mono) load from Google Fonts. If your vault is offline-first, mirror them into `fonts/` and rewrite the `@import`s to local `@font-face` declarations.

---

## License

Theme: use freely inside your Grimheim vault. Don't redistribute the *Grimheim Gothic* font outside this package — it's the brand display face.
