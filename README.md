# UX Skills for Claude

A collection of 16 structured skill files that teach Claude UX best practices
across every major category of mobile and web product design. Each skill covers
a focused topic with a checklist, design patterns, and decision frameworks —
all written to be read and applied by Claude during a conversation.

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

The skills are designed for teams building mobile apps on iOS, Android, and the web.

---

## Skills

| Folder | Category | What it covers |
|---|---|---|
| `general` | General App Quality | App store, launch, platform parity, OS integrations, versioning |
| `search` | Search | Discoverability, autocomplete, filters, empty states, voice, typo tolerance |
| `forms` | Forms | Input types, validation, keyboard behavior, autofill, multi-step flows |
| `user-account` | User Account | Login, logout, social auth, gestures, account deletion, session management |
| `visual-design` | Visual Design | Typography, color, spacing, icons, animation, dark mode, RTL layout |
| `navigation` | Navigation | Tab bars, back buttons, deep links, 3-tap rule, modal vs push |
| `information-architecture` | Information Architecture | Content structure, labeling, sort, filter, settings organization |
| `accessibility` | Accessibility | WCAG 2.1, screen readers, contrast, touch targets, reduce-motion |
| `content` | Content and UX Writing | Plain language, microcopy, UGC, localization, content freshness |
| `utility` | Utility | Favorites, share sheet, in-app browser, personalization, clipboard |
| `network` | Network | Offline mode, slow connection, error states, background sync |
| `safety-privacy` | Safety and Privacy | Biometrics, permissions, 2FA, GDPR, data protection |
| `settings` | Settings | Settings structure, theme, font size, notification granularity |
| `help-onboarding` | Help and Onboarding | First-run flow, skeleton screens, tooltips, in-app help |
| `error-handling` | Error Handling | Confirmation dialogs, undo, error messages, crash recovery |
| `ai-automation` | AI and Automation | AI transparency, recommendations, feedback loops, on-device vs cloud |

---

## How to Use in Claude Code

Claude Code reads skill files automatically when they are placed in the right
location. Follow these steps to install the skills and start using them.

### 1. Clone this repository

```bash
git clone https://github.com/parhamb/design-skills.git
```

### 2. Place the skills folder in your project

Claude Code looks for skills in a `.claude/skills/` folder at the root of your project.

```bash
cp -r design-skills/ your-project/.claude/skills/ux/
```

Your project structure should look like this:

```
your-project/
├── .claude/
│   └── skills/
│       └── ux/
│           ├── general/
│           │   └── SKILL.md
│           ├── search/
│           │   └── SKILL.md
│           ├── forms/
│           │   └── SKILL.md
│           └── ... (all 16 skill folders)
├── src/
└── CLAUDE.md
```

### 3. Reference the skills in your CLAUDE.md (optional)

If you want Claude to always be aware of the skills, add a note in your
`CLAUDE.md` file at the project root:

```markdown
## Skills

UX skills are available in `.claude/skills/ux/`. Use them when reviewing
screens, auditing flows, or giving product feedback.
```

### 4. Talk to Claude normally

Once the skills are in place, Claude reads the relevant skill file automatically
based on what you ask. No commands needed.

```
You: Review the onboarding flow in my app.
Claude: [reads help-onboarding/SKILL.md and applies the checklist]

You: What should I check for accessibility on this screen?
Claude: [reads accessibility/SKILL.md and walks through the items]

You: Is this navigation structure good for mobile?
Claude: [reads navigation/SKILL.md and gives structured feedback]
```

---

## Customizing a Skill

Each `SKILL.md` is a plain markdown file. Open any of them and edit the
checklist items, add patterns specific to your product, or adjust guidance
to match your team's conventions.

```bash
# Example: add a company-specific rule to the forms skill
open .claude/skills/ux/forms/SKILL.md
```

Changes take effect immediately in the next conversation.

---

## License

MIT — see [LICENSE](./LICENSE)
