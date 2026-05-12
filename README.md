# 👻 Ghostwriter Skill — AI Text Humanizer for Perplexity

> **The #1 AI text humanizer skill for Perplexity AI.** Transform AI-generated content into natural, human-like writing that bypasses GPTZero, Turnitin, Originality.ai, and Copyleaks — from a 5-word WhatsApp reply to a 10,000-word blog post.

<!-- SEO keywords: ai text humanizer, humanize ai text, ai content humanizer, bypass ai detection, ai writing humanizer, perplexity skill, ghostwriter ai, ai to human text converter, remove ai detection, ai text rewriter, chatgpt text humanizer, make ai text sound human -->

**👉 Claude version:** [ghostwriter-artifact](https://github.com/prakash-connects/content-humanizer-artifact) | **Also known as:** `ai-text-humanizer-skill` `ai-content-humanizer` `humanize-ai-writing`

[![MIT License](https://img.shields.io/badge/license-MIT-green.svg)](./LICENSE)
[![Platform](https://img.shields.io/badge/platform-Perplexity%20AI-blue.svg)](https://perplexity.ai)
[![Version](https://img.shields.io/badge/version-2.0-orange.svg)](./SKILL.md)
[![Works With](https://img.shields.io/badge/also%20works%20with-Claude%20%7C%20GPT%20%7C%20Gemini-purple.svg)](./SKILL.md)

---

## What Is This?

**Ghostwriter Skill** is a precision AI text humanizer built on the actual science behind how AI detectors work. It doesn’t just swap words — it targets the three detection layers every major AI detector uses:

| Detection Layer | What AI Detectors Check | What Ghostwriter Does |
|---|---|---|
| **Perplexity (PPL)** | Is the text too statistically predictable? AI = <60 PPL | Raises your text above 85 PPL |
| **Burstiness (B)** | Are all sentences the same length? AI = <0.2 B | Injects rhythm variation above 0.4 B |
| **Classifier Patterns** | BERT-flagged transition phrases + RLHF verbosity | Removes 30+ AI-isms completely |

### Supported Formats
📱 WhatsApp / casual chat · 💼 LinkedIn posts · 🌐 Quora / forum answers · 📝 Blog posts (up to 10,000 words) · 📧 Email · 💬 Comments & replies

---

## Quick Install — Perplexity AI

1. Open [Perplexity.ai](https://perplexity.ai)
2. Copy the full contents of [`SKILL.md`](./SKILL.md)
3. Paste it as your system/project instruction
4. Paste any AI-generated text and ask to humanize it

> Minimal prompt: just paste your content — Ghostwriter auto-detects platform and tone.

---

## Quick Install — Claude AI

1. Open [Claude.ai](https://claude.ai) → New Project → **Project Instructions**
2. Copy [`SKILL.md`](./SKILL.md)
3. Paste as system instruction
4. Done — every chat in that project is now a Ghostwriter session

> For the Claude-native artifact format: [ghostwriter-artifact](https://github.com/prakash-connects/content-humanizer-artifact)

---

## Quick Install — API (Any Model)

```python
import anthropic  # or openai, groq, etc.

with open("SKILL.md", "r") as f:
    system_prompt = f.read()

client = anthropic.Anthropic(api_key="YOUR_API_KEY")

response = client.messages.create(
    model="claude-opus-4-5",
    max_tokens=4096,
    system=system_prompt,
    messages=[{
        "role": "user",
        "content": "Platform: LinkedIn\n\nHumanize this:\n\nIt is important to note that AI has significantly transformed marketing. Moreover, businesses must adapt to remain competitive."
    }]
)
print(response.content[0].text)
```

---

## How to Use

```
Platform: [LinkedIn / WhatsApp / Blog / Quora / Email / Comment / General]
Tone: [Casual / Professional-Conversational / Formal]
Length: [Preserve / Tighten / Expand]

[Paste your AI-generated content here]
```

**Minimal use:** Just paste your text — auto-detection handles the rest.

---

## What It Removes (AI-ism Ban List)

Ghostwriter hard-bans **30+ AI-isms** that trigger every major AI detector:

```
Moreover · Furthermore · Indeed · Consequently · In conclusion · To summarize
It's important to note · This underscores · This highlights · Needless to say
At the end of the day · In today’s fast-paced world · In the ever-evolving landscape
Leverage (metaphorical) · Utilize · Delve into · Deep dive · Navigate the landscape
Tapestry · Pivotal · Meticulous · Vibrant · Realm · Showcasing · Seamlessly
Game-changer · Revolutionary · Groundbreaking · Paradigm shift · In order to
```

---

## Transformation Example

**Before (High AI Risk — GPTZero flags this):**
> “It is important to note that artificial intelligence has significantly transformed the marketing landscape. Moreover, businesses must adapt to these changes to remain competitive. Furthermore, those who fail to embrace this technology may find themselves at a disadvantage.”

**After — LinkedIn (Low AI Risk):**
> “Here’s what I’ve noticed — AI has completely shaken up how we do marketing. The companies rolling with it are pulling ahead fast. And the ones dragging their feet? They’re going to feel it. Not someday. Now.”

**Changes made:** Eliminated 3 Tier-1 banned phrases · Injected burstiness (4 varied sentences) · Added first-person observation · Fragment ending for punch.

---

## Features at a Glance

| Feature | Description |
|---|---|
| 📊 **Perplexity Elevation** | Raises PPL above human baseline (>85) |
| 🔀 **Burstiness Injection** | Forces sentence length variation every paragraph |
| 🚫 **AI-ism Removal** | 30+ hard-banned phrases, 8 soft-limit phrases |
| 🎤 **Voice Injection** | Contractions, first-person, emotional investment |
| 🎯 **Platform Optimization** | WhatsApp to 10k-word articles — tone-matched |
| ✅ **Self-Validation Loop** | 9-point checklist before every output |
| 📀 **Long-form Ready** | Handles up to 10,000 words with burstiness resets |

---

## Files

```
content-humanizer-skill/  (also: ghostwriter-skill, ai-text-humanizer-skill)
├── SKILL.md              ← Main skill file — paste into Perplexity or Claude
├── README.md             ← This file
├── examples/
│   ├── whatsapp.md       ← WhatsApp transformation example
│   ├── linkedin.md       ← LinkedIn post transformation example
│   └── blog.md           ← Blog post transformation example
└── LICENSE               ← MIT License
```

---

## Ethical Use

✅ Rephrasing your own AI-assisted drafts · Professional content refinement · Marketing copy · Personal writing improvement

❌ Academic fraud · Impersonation · Misinformation · Harassment

---

## Related

- **Claude Artifact version:** [prakash-connects/content-humanizer-artifact](https://github.com/prakash-connects/content-humanizer-artifact)

---

## Also Known As

`ghostwriter-skill` · `ai-text-humanizer` · `ai-content-humanizer` · `humanize-ai-text` · `ai-writing-humanizer` · `bypass-ai-detection` · `chatgpt-humanizer` · `ai-to-human-text` · `remove-ai-detection` · `perplexity-skill-humanizer`

---

## License

MIT — free to use, modify, and share with attribution.

---

## Author

**Prakash Behera** — [@prakash-connects](https://github.com/prakash-connects)

*Built on the actual science of how AI detectors work — not guesswork.*
