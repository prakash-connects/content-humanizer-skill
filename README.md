# 🧠 Content Humanizer — Perplexity Skill v2.0

> Transform AI-generated text into natural, human-like writing — from a 5-word WhatsApp reply to a 10,000-word blog post. Powered by NLP detection science: perplexity elevation, burstiness injection, and full AI-ism removal.

**👉 Also available as a Claude Artifact:** [content-humanizer-artifact](https://github.com/prakash-connects/content-humanizer-artifact)

---

## What This Is

A precision content humanization skill built on the actual science behind how AI detectors (GPTZero, Turnitin, Originality.ai, Copyleaks) work. It doesn't just swap words — it targets the three detection layers:

- **Perplexity** — raises unpredictability score above human baseline (>85 PPL)
- **Burstiness** — injects dramatic sentence rhythm variation (>0.4 B score)
- **Classifier patterns** — removes BERT-flagged transition phrases and RLHF-induced verbosity

**Supports every format:**
- 📱 WhatsApp / casual chat
- 💼 LinkedIn posts
- 🌐 Quora / forum answers
- 📝 Blog posts and articles (up to 10,000 words)
- 📧 Email (cold outreach to internal comms)
- 💬 Comment replies

---

## How to Use — Perplexity

### Load as a Perplexity Skill
1. Open [Perplexity.ai](https://perplexity.ai)
2. In your conversation, trigger skill loading with: `load_skill content-humanizer`
3. Once loaded, paste your content and specify platform/tone
4. Perplexity will apply the full humanization workflow

### Direct Prompt Use
Copy the full contents of [`SKILL.md`](./SKILL.md) and paste it as a system prompt in any AI interface.

---

## How to Use — Claude

> For the Claude-specific version with artifact format, see: [content-humanizer-artifact](https://github.com/prakash-connects/content-humanizer-artifact)

### Option A — Claude Project (Recommended)
1. Open [Claude.ai](https://claude.ai) → New Project → **Project Instructions**
2. Copy the full contents of [`SKILL.md`](./SKILL.md)
3. Paste as the project system instruction
4. Paste any AI-generated content in chat to humanize it

### Option B — Claude API
```python
import anthropic

with open("SKILL.md", "r") as f:
    system_prompt = f.read()

client = anthropic.Anthropic(api_key="YOUR_API_KEY")

message = client.messages.create(
    model="claude-opus-4-5",
    max_tokens=4096,
    system=system_prompt,
    messages=[
        {
            "role": "user",
            "content": "Platform: LinkedIn\n\nHumanize this:\n\nIt is important to note that AI has significantly transformed marketing. Moreover, businesses must adapt to remain competitive."
        }
    ]
)
print(message.content[0].text)
```

---

## Prompt Format

```
Platform: [LinkedIn / WhatsApp / Blog / Quora / Email / Comment / General]
Tone: [Casual / Professional-Conversational / Formal]
Length: [Preserve / Tighten / Expand]

[Paste your content here]
```

Minimal use: just paste the text — skill auto-detects platform and applies Professional-Conversational tone.

---

## What It Does

| Technique | What It Targets |
|---|---|
| **Perplexity Elevation** | Raises PPL score by using surprising-but-accurate word choices |
| **Burstiness Injection** | Forces sentence length variation: short punchy + long complex |
| **AI-ism Removal** | Strips "Moreover", "Furthermore", "delve into", "tapestry" + 30 more |
| **Structural Humanization** | Irregular paragraph lengths, organic transitions |
| **Voice Injection** | First-person hooks, contractions, emotional investment |
| **Platform Optimization** | Tone-matched output for each platform from WhatsApp to 10k-word articles |
| **Self-Validation Loop** | Built-in 9-point checklist run before every output |

---

## Example

**Before (High AI Risk):**
> "It is important to note that artificial intelligence has significantly transformed the marketing landscape. Moreover, businesses must adapt to these changes to remain competitive. Furthermore, those who fail to embrace this technology may find themselves at a disadvantage."

**After — LinkedIn (Low AI Risk):**
> "Here's what I've noticed — AI has completely shaken up how we do marketing. The companies rolling with these changes are pulling ahead fast. And the ones dragging their feet? They're going to feel it. Not someday. Now."

---

## Files

```
content-humanizer-skill/
├── SKILL.md              ← Main skill file (load this in Perplexity or paste in Claude)
├── README.md             ← This file
├── examples/
│   ├── whatsapp.md       ← WhatsApp reply transformation example
│   ├── linkedin.md       ← LinkedIn post transformation example
│   └── blog.md           ← Blog post transformation example
└── LICENSE               ← MIT License
```

---

## Ethical Use

✅ Rephrasing your own AI-assisted drafts · Professional content refinement · Marketing copy · Educational materials

❌ Academic fraud · Impersonation · Misinformation · Harassment

---

## Related

- **Claude Artifact version:** [prakash-connects/content-humanizer-artifact](https://github.com/prakash-connects/content-humanizer-artifact)

---

## License

MIT — free to use, modify, and share with attribution.

---

## Author

**Prakash Behera** — [@prakash-connects](https://github.com/prakash-connects)

*Built on the actual science of how AI detectors work — not guesswork.*
