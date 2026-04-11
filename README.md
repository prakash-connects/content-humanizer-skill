# 🧠 Content Humanizer — Claude AI Skill

> Transform AI-generated text into natural, human-like writing while preserving professional quality and original meaning.

---

## What This Is

A structured Claude AI skill (system prompt + instruction set) that detects AI writing patterns and rewrites content to sound authentically human — designed for legitimate professional and educational use.

**Supports:**
- ✅ LinkedIn posts
- ✅ Quora answers
- ✅ Articles & blog posts
- ✅ Comment replies
- ✅ General professional writing

---

## How to Use

### Option 1 — Paste as System Prompt (Claude.ai / API)
1. Open [Claude.ai](https://claude.ai) → New Project → **Project Instructions**
2. Copy the full contents of [`SKILL.md`](./SKILL.md)
3. Paste it as the system/project instruction
4. Start chatting — paste any AI-generated text and ask Claude to humanize it

### Option 2 — Use via Claude API
```python
import anthropic

with open("SKILL.md", "r") as f:
    system_prompt = f.read()

client = anthropic.Anthropic(api_key="YOUR_API_KEY")

message = client.messages.create(
    model="claude-opus-4-5",
    max_tokens=2048,
    system=system_prompt,
    messages=[
        {
            "role": "user",
            "content": "Platform: LinkedIn\n\nHumanize this:\n\nIt is important to note that artificial intelligence has significantly transformed the marketing landscape. Moreover, businesses must adapt to these changes to remain competitive."
        }
    ]
)

print(message.content[0].text)
```

### Option 3 — Load as Custom Skill (Advanced Setups)
If you're building a custom AI assistant or agent pipeline that supports skill loading, reference `SKILL.md` directly using the frontmatter metadata:

```yaml
name: content-humanizer
version: 1.0
```

---

## Prompt Format

When using this skill, structure your message like this:

```
Platform: [LinkedIn / Quora / Article / Comment / General]
Tone: [Keep formal / Go casual / Professional-conversational]

[Paste your AI-generated content here]
```

**Minimal usage** — just paste the text and Claude will apply general humanization automatically.

---

## What It Does

| Technique | Description |
|---|---|
| **Perplexity boost** | Replaces predictable word choices with contextually richer alternatives |
| **Burstiness** | Mixes short punchy sentences with longer complex ones for natural rhythm |
| **AI marker removal** | Strips "Moreover," "Furthermore," "It's important to note," etc. |
| **Tone variation** | Fluctuates between formal and conversational within professional bounds |
| **Personal voice** | Adds subtle first-person hooks and experiential references |
| **Platform adaptation** | Formats and tones for LinkedIn, Quora, articles, or comments |

---

## Example

**Before:**
> "It is important to note that artificial intelligence has significantly transformed the marketing landscape. Moreover, businesses must adapt to these changes to remain competitive."

**After (LinkedIn):**
> "Here's what I've noticed — AI has completely shaken up how we do marketing. Companies rolling with these changes are pulling ahead fast. The ones dragging their feet? They're going to feel it. Not someday. Now."

---

## Files

```
content-humanizer-skill/
├── SKILL.md              ← The main skill/system prompt (copy this into Claude)
├── README.md             ← This file
├── examples/
│   ├── linkedin.md       ← LinkedIn post example transformation
│   ├── quora.md          ← Quora answer example transformation
│   └── article.md        ← Article/blog example transformation
└── LICENSE               ← MIT License
```

---

## Ethical Use

This skill is intended for:
- ✅ Rephrasing your own AI-assisted drafts for authentic publishing
- ✅ Learning how to write more naturally
- ✅ Professional content refinement
- ❌ Academic fraud or plagiarism
- ❌ Impersonation or deception
- ❌ Spreading misinformation

---

## Contributing

Pull requests welcome. If you add new platform-specific instructions (e.g., Twitter/X, email newsletters, Reddit), please follow the existing format in `SKILL.md` and add a matching example in `examples/`.

---

## License

MIT — free to use, modify, and share with attribution.

---

## Author

**Be Prakash**
- 🐙 GitHub: [@beingbe98](https://github.com/beingbe98)
- 💼 Co-founder, [Aromasymphonies Private Limited](https://aromasymphonies.com)
- 📍 Chennai, India

---

*Built for professionals who use AI as a drafting tool but want their published voice to sound like them.*
