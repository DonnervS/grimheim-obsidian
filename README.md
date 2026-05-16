# Grimheim — Obsidian Theme

A grim-dark fantasy tabletop snippet for **Obsidian**. Built for **Grimheim** GM vaults: warbands, missions, factions, lore.

Drop-in CSS snippet — works on top of Obsidian's default theme. **Use with dark mode.**

---

## What's in this package

```
grimheim-obsidian/
├── snippets/
│   ├── grimheim.css            ← the snippet
│   └── fonts/
│       └── GrimheimGothic-Thin.otf
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

### 1. Copy the snippet into your vault

In your vault folder, find the hidden folder `.obsidian/snippets/`
(create it if it doesn't exist).

Copy **both** of these into it, keeping the folder structure:

```
.obsidian/snippets/grimheim.css
.obsidian/snippets/fonts/GrimheimGothic-Thin.otf
```

The CSS expects the font at `fonts/GrimheimGothic-Thin.otf` relative to itself.

### 2. Enable it in Obsidian

`Settings → Appearance → CSS snippets → ⟳ reload → toggle "grimheim" on`

Make sure base color scheme is set to **Dark**.

### 3. (Optional) Install the templates

Copy everything from `templates/` into a folder in your vault, e.g. `Templates/`. Then:

`Settings → Templates → Template folder location` → point it at that folder.

Insert a template into any note with the command **Templates: Insert template** (bind it to a hotkey if you use it often).

---

## Templates

Five blank, reusable note templates ship in `templates/`. Each is built for the **core Templates plugin** — it fills `{{title}}` from the note name and `{{date}}` from today's date on insert. Every template is wired to the snippet's headings, tables, and custom callouts.

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

## Variant classes

The snippet ships with opt-in flags. Add a class to `<body>` to flip a variant.
The fastest way is the **Style Settings** plugin (`Settings → Community plugins`) which exposes these as toggles automatically. Otherwise: use a CSS snippet like

```css
body { /* pick what you want */ }
body.gh-callout-parchment {}
body.gh-heading-fell      {}
body.gh-grain             {}
body.gh-dropcap           {}
```

| Class | Effect |
|---|---|
| *(none)* | Default — Gothic display headings, iron-seal callouts |
| `gh-heading-fell` | H1/H2 swap to **IM Fell English SC** (less bold, more antiquarian) |
| `gh-callout-woodcut` | Callouts get a double-stroke woodcut frame |
| `gh-callout-parchment` | Callouts render as parchment slips with iron-stamp header |
| `gh-grain` | Subtle paper-grain overlay across notes |
| `gh-dropcap` | First paragraph of every note gets an IM Fell English drop-cap |

You can stack them: `body.gh-dropcap.gh-grain.gh-callout-parchment` etc.

---

## Custom callouts

In addition to Obsidian's built-in `[!note]`, `[!warning]`, etc., this snippet styles five Grimheim-specific callouts:

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

The snippet doesn't ship icons — Obsidian uses Lucide internally and that's left alone. Inside notes, prefer the dingbats:

`✠   ☠   †   ⚔   ⛓   ☾   ✦`

**No emoji.**

---

## Replacing / extending

- All tokens are prefixed `--gh-*` and defined at the top of `grimheim.css`. Override them in a downstream snippet to retint.
- The CSS targets both **Live Preview** (`.cm-header-*`, `.HyperMD-*`) and **Reading View** (`.markdown-preview-view`). Keep both updated if you edit headings.
- Body and accent faces (Vollkorn, IM Fell English, Manrope, JetBrains Mono) load from Google Fonts. If your vault is offline-first, mirror them into `fonts/` and rewrite the `@import`s to local `@font-face` declarations.

---

## License

Theme: use freely inside your Grimheim vault. Don't redistribute the *Grimheim Gothic* font outside this package — it's the brand display face.
