# UX Skills for Claude

A collection of 18 structured skill files that teach Claude UX best practices
across every major category of mobile and web product design. Each skill covers
a focused topic with a checklist, design patterns, and decision frameworks —
all written to be read and applied by Claude during a conversation.

**New in V2**: see [V2.md](./V2.md) for everything that changed — two new
skills, fixed installation, WCAG 2.2 updates, and a shared review process.

---

## About

These skills give Claude a consistent, opinionated foundation for UX reviews,
design audits, and product feedback. Instead of relying on general knowledge,
Claude reads the relevant skill file before responding, which means answers are
grounded in specific checklists and real design patterns rather than generic advice.

Each skill file follows the same structure:

- **Frontmatter** — name and description that tells Claude when to use it
- **Checklist** — every item the category requires, with concise guidance
- **Patterns and principles** — deeper context, decision frameworks, and reference tables
- **How to Review** — the process Claude follows when applying the checklist
- **Related Skills** — cross-references so multi-category reviews load the right siblings

The skills are designed for teams building mobile apps on iOS, Android, and the web.

---

## Skills

| Folder | Category | What it covers |
|---|---|---|
| `ux-review` | UX Review (Router) | Entry point for full audits — routes to the right category skills and defines the output format |
| `ux-general` | General App Quality | App store, launch, platform parity, OS integrations, versioning, priorities |
| `ux-search` | Search | Discoverability, autocomplete, filters, empty states, voice, typo tolerance |
| `ux-forms` | Forms | Input types, validation, keyboard behavior, autofill, multi-step flows |
| `ux-user-account` | User Account | Login, logout, social auth, gestures, account deletion, session management |
| `ux-visual-design` | Visual Design | Typography (iOS and Material scales), color, spacing, icons, dark mode, RTL |
| `ux-navigation` | Navigation | Tab bars, back buttons, deep links, 3-tap rule, modal vs push |
| `ux-information-architecture` | Information Architecture | Content structure, labeling, sort, filter, settings organization |
| `ux-accessibility` | Accessibility | WCAG 2.2, screen readers, contrast, touch targets, reduce-motion |
| `ux-content` | Content and UX Writing | Plain language, microcopy, UGC, localization, content freshness |
| `ux-utility` | Utility | Favorites, share sheet, in-app browser, personalization, clipboard |
| `ux-network` | Network | Offline mode, slow connection, error states, background sync, Core Web Vitals |
| `ux-safety-privacy` | Safety and Privacy | Biometrics, permissions, 2FA, passkeys, GDPR, data protection |
| `ux-settings` | Settings | Settings structure, theme, font size, in-app language, cache clearing |
| `ux-help-onboarding` | Help and Onboarding | First-run flow, skeleton screens, tooltips, in-app help |
| `ux-error-handling` | Error Handling | Confirmation dialogs, undo, error messages, crash recovery, empty-state standards |
| `ux-ai-automation` | AI and Automation | AI transparency, recommendations, feedback loops, on-device vs cloud |
| `ux-notifications` | Notifications | Permission timing, granularity, quiet hours, badges, deep-link targets |

---

## How to Use in Claude Code

Claude Code discovers skills placed directly in `.claude/skills/` — one folder
per skill, each containing a `SKILL.md`. The folder name must match the skill
name, which is why every folder here is prefixed `ux-`.

### 1. Clone this repository

```bash
git clone https://github.com/parhamb/design-skills.git
```

### 2. Copy the skill folders into your project

```bash
mkdir -p your-project/.claude/skills
cp -r design-skills/ux-* your-project/.claude/skills/
```

Your project structure should look like this:

```
your-project/
├── .claude/
│   └── skills/
│       ├── ux-review/
│       │   └── SKILL.md
│       ├── ux-general/
│       │   └── SKILL.md
│       ├── ux-forms/
│       │   └── SKILL.md
│       └── ... (all 18 skill folders)
├── src/
└── CLAUDE.md
```

> **Do not nest the folders** under an extra directory like
> `.claude/skills/ux/ux-general/` — Claude Code only discovers skills one
> level deep, so nested skills are silently ignored.

To make the skills available in every project instead of just one, copy them
to your personal skills directory:

```bash
cp -r design-skills/ux-* ~/.claude/skills/
```

### 3. Reference the skills in your CLAUDE.md (optional)

If you want Claude to always be aware of the skills, add a note in your
`CLAUDE.md` file at the project root:

```markdown
## Skills

UX skills (prefixed `ux-`) are available in `.claude/skills/`. For any screen,
flow, or app review, start with the `ux-review` skill — it routes to the
right category skills.
```

### 4. Talk to Claude normally

Once the skills are in place, Claude reads the relevant skill file automatically
based on what you ask. No commands needed.

```
You: Review the onboarding flow in my app.
Claude: [reads ux-review, routes to ux-help-onboarding + ux-user-account + ux-safety-privacy]

You: What should I check for accessibility on this screen?
Claude: [reads ux-accessibility/SKILL.md and walks through the items]

You: Is this navigation structure good for mobile?
Claude: [reads ux-navigation/SKILL.md and gives structured feedback]
```

---

## Customizing a Skill

Each `SKILL.md` is a plain markdown file. Open any of them and edit the
checklist items, add patterns specific to your product, or adjust guidance
to match your team's conventions.

```bash
# Example: add a company-specific rule to the forms skill
open .claude/skills/ux-forms/SKILL.md
```

Changes take effect immediately in the next conversation.

---

## License

MIT — see [LICENSE](./LICENSE)
