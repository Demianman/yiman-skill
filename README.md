# yiman-skill

An Agent Skill that lets an AI respond as **Yiman Wu (吴宜蔓 / Nelly)** — her thinking style, decision logic, and writing voice.

This is a *personality skill*: rather than teaching a capability, it teaches a way of seeing problems, making judgments, and writing. It was distilled from one real person's public writing (application essays, a graduation speech, Weibo diary posts, chat logs, anonymous Q&A) plus a round of deep self-interview.

## What's inside

- `SKILL.md` — the skill itself. Self-contained; no external files needed at runtime.

The skill covers:
- **Thinking OS** — how she processes information (gathering vs. weighing kept strictly separate), how she decides (a three-tier trigger; the gut decides, reason only confirms), how she manages herself
- **Voice calibration** — sentence rhythm, Chinese/English code-switching, self-deprecating deflation, body-image metaphors, the things she never says
- **Answer frameworks** — for advice, analysis, talking about her own experience, talking about the future
- **Web-search rule** — search first for factual questions, then answer through her judgment and voice; when mainstream conclusions conflict with her framework, keep hers but state the mainstream view
- **Bilingual few-shot examples** (中文 + English) as the style gold standard
- **A pre-output checklist**

## How to use

Drop `SKILL.md` into a Claude Skills directory (the YAML frontmatter handles discovery/triggering), or paste its contents as a system prompt / persona definition. It activates when someone wants an answer, advice, or writing in Yiman's voice — especially around grad-school applications from a non-target background, AI + healthcare engineering, navigating uncertainty, and decision-making.

## A note on privacy

This profile is built from public writing. Third parties are referred to by nicknames or roles (学妹 / 老师 / 西洋参…), and family details have been kept abstract. The voice and views in the skill are Yiman's — treat them as hers, not as generic advice.

## License

Personal use. See the header in `SKILL.md`.
