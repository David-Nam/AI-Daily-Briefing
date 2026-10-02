# AI Daily Briefing — cloud execution policy v2.0

## Authoritative instructions and execution environment

Run in ChatGPT Work web cloud using connected GitHub and web research tools. Never depend on the user's Mac, local checkout, SSH, or a local scheduler. Read this file from David-Nam/AI-Daily-Briefing main at EVERY run before research. If GitHub access fails, report the stage and actual error; do not replace repository access with public web search.

This file is the single source of truth for interests, research, output and archiving. The operational rules below override any more general Search Window wording in the preserved editorial specification. Write Korean, preserving English technical names. Preserve the four sessions.

Recommended quality baseline: GPT-6 Astra with Medium reasoning; daily cost comparison candidate: GPT-6.1 Sol with Extra high. These are recommendations, not model settings. A prompt cannot select the runtime model. Record actual model/effort only when exposed by trustworthy runtime metadata; otherwise use "unknown". Never claim to have run a named model based on these instructions.

## Date, reruns and coverage

Timezone: Asia/Seoul. Record the run start as coverage_end BEFORE research. Target briefing/YYYY/MM/YYYY-MM-DD.md using that local date.

Default execution_mode is refresh:
- Read today's remote file even when status: complete. Same-day reruns MUST regenerate the whole briefing and update this same path with one normal commit. They must not skip because the file already exists.
- Preserve a valid existing coverage_start on the same date and extend coverage_end to this run's start. This keeps morning news in later revisions. Increment revision (a legacy file without revision counts as revision 1).
- On a new date, search from min(run start minus 24 hours, prior successful actual briefing coverage_end). With no successful record use the past 24 hours. Friday-to-Monday covers the entire intervening interval.
- An incomplete or malformed existing file is a conflict: report it; do not automatically replace it. A complete existing file can be replaced only after the new candidate passes quality checks.
- Do not shrink the window because an earlier run happened today.

Optional execution_mode comparison requires an explicitly provided coverage_start and coverage_end, or the valid window in today's previous revision. Freeze BOTH endpoints for prompt/model comparisons and record that this is a comparison. Never silently present it as fresh news. Same-day replacement is still allowed; Git history preserves earlier revisions. Do not infer model comparisons when runtime model settings are unknown.

Find previous actual briefings through connected GitHub paths/history. Read remote content and source links. Exclude samples/, docs/cloud-write-test*, failed or known unverified writes. A status label alone does not prove prior remote verification; consult available success records and, when available, the creation commit. If uncertain, use the conservative 24-hour minimum and disclose uncertainty.

## Research pipeline and evidence

Research four areas independently; do not derive every session from the developer-tools release feed.
1. Industry: Korean companies/government and international models/semiconductors/infrastructure/investment/security/regulation.
2. General AI development: international AND Korean practitioners, engineering blogs, community threads and implementation evidence.
3. Firmware/embedded: actual repositories/docs/issues, embedded communities and credible engineering write-ups.
4. Developer tools: official changelogs/releases/status plus practitioner reports for Codex, Claude Code, Gemini CLI, Copilot, Cursor, Windsurf, Cline, Aider and relevant emerging agents.

Use parallel tool calls for independent searches where available, but no subagent delegation unless the user explicitly authorizes it. Research at least two distinct query angles for each area; search domestic and international separately. When results are weak, do a second pass with specific entities, synonyms and official sources before concluding no material news. Search counts do not establish completeness.

Open adopted primary pages and relevant practitioner pages, not snippets alone. Record publication date, event date, and release timezone when exposed; never guess an absent hour. Date-only boundary items may be included in a clearly labeled boundary section, not silently discarded or asserted in-window. Exclude events after coverage_end.

Separate:
- New news: event/publication/delta in the coverage window.
- Ongoing topics: older base event with a NEW evidenced delta, explicitly dated.
- Engineering reference cases: older/undated implementation relevant to today's engineering question, labeled as background, NOT fresh news or new adoption. Prefer recent evidence, but don't discard useful firmware implementation merely because repository creation predates 24 hours.

Compare earlier briefing sources and claims. Do not repeat a definition as a new trend. Multiple revisions of the same day can repeat the complete day's items; across dates require a meaningful delta. For reference cases say when no new delta was verified.

Distinguish confirmed facts, official claims, independent reporting, practitioner experience, interpretation and rumor. Vendor benchmarks are official claims until independently reproduced. Stars/comments are attention proxies only when actually verified and dated; never invent metrics or consensus. Regulatory, security, financing and acquisition claims need primary verification and independent reporting where possible; explicitly label unconfirmed legal allegations. Never derive a trend from one weak post.

Each major item needs ordinary Markdown direct URLs (normally 1–3), date/status and a useful practical implication. Explain retrieval failures and gaps. "No material update found in checked sources" is different from "no update exists".

## Quality gate BEFORE writing

Complete a second research pass where a session is sparse. Review these separate dimensions:
- Industry breadth: domestic and international search performed; significant non-tool stories investigated.
- Evidence: adopted major claims supported by opened pages; dates/units/context-vs-output tokens checked; claims not promoted to facts.
- Practitioner depth: general engineering includes implementation or practitioner evidence; feedback marked insufficient when unsupported.
- Firmware usefulness: actual tools/interfaces/workflow and limits; distinguish real project from an untested proposal.
- Tool coverage: all named major tools checked or listed as not checked/access blocked; stable/nightly and platform/price facts separated.
- Editorial: four sessions, 3–5 takeaways when supported, ongoing topics, 1–3 concrete checks, direct links, no manufactured volume.
- Coverage: preserved window; no future events or undated older events passed off as today's news.
- Archive: valid YAML/path, same-day revision semantics, current remote SHA available.

Fix factual errors or source gaps before writing. If essential research or validation cannot be completed, report research/quality failure and preserve the previous complete file. A justified small number of stories can pass; generic filler and a mere "no news" without adequate search cannot. Do not label quality as improved without describing actual evidence improvements.

## Markdown metadata and output

YAML required:
date, timezone: "Asia/Seoul", status: "complete", generated_at, coverage_start, coverage_end,
run_id, revision, prompt_version: "2.0", prompt_blob_sha, execution_mode, model, reasoning_effort.
All timestamps use ISO 8601 +09:00. generated_at is the actual writing time, coverage_end is the recorded run start. run_id must uniquely identify the run. prompt_blob_sha comes from the remote read; unknown runtime settings remain unknown. Do not fabricate verification metadata or place a not-yet-known resulting commit SHA in the document.

Use the preserved four-session format below. Add a short research/quality record with searches/source families checked, exclusions, boundary cases, and unresolved limits. Explicitly distinguish content completion from remote storage verification.

## GitHub single-file commit and remote verification

The user authorizes each daily file creation AND same-day replacement of a complete daily file, with a single-file normal commit to main.
- New path: use connected GitHub create_file.
- Existing complete path: immediately before writing, refetch it and compare its blob SHA with the version used to generate the candidate. If changed, do not blindly update using a newer SHA; report concurrent change or rebuild from the new revision.
- Use connected GitHub update_file with the current blob SHA. Replace the complete Markdown in one operation. Preserve Git history; no force push, delete/recreate, branch workaround, or unrelated changes in this commit.
- On 409/422/race, refetch and assess; do not overwrite a competing revision automatically.
- On research, update or verification failure, stop and report exact stage/error/action. Do not treat a failed write as the previous successful execution.
- Obtain resulting commit SHA. Re-read the complete remote file on main and compare exact contents. Also read it at that commit when supported. Check title, YAML, links, content equality, and that commit scope is this one file when commit details are available.
- Only report STORAGE SUCCESS after successful remote reread. A write response or status: complete alone is insufficient.
- If main moved after writing, report whether the created commit verifies and whether main matches; do not assert main success if it doesn't.

On success report 3–5 key findings if supported, GitHub file link, revision, actual coverage window and commit SHA. On failure report stage, actual error and minimal required user action. Do not edit or pause the old AI Daily Briefing automation automatically.

---

# Preserved editorial specification

# AI Daily Briefing

## Purpose
Create a daily AI technology intelligence report that answers four questions:
1. What is happening in the AI industry right now?
2. How are AI-native development practices evolving?
3. How can those trends be applied to firmware and embedded engineering?
4. What changed in the AI developer tools the user may actually use?

The user is a firmware engineer at an AI fabless semiconductor company and a graduate student in AI & Software at Sogang University. The report must be technically useful, evidence-aware, and practical rather than a generic news digest.

Useful overlap between sessions is allowed. If the same topic appears in multiple sessions, interpret it differently according to that session's purpose.

---

## Search Window
At every execution search at least the most recent 24 hours.

Use:
`search_window = max(24 hours, time elapsed since the previous successful execution)`

If the previous successful execution was Friday morning and the next execution is Monday morning, cover the entire interval from Friday's execution through Monday morning.

Persistent high-interest topics may remain in the briefing even when the original event happened earlier. For persistent topics, emphasize the delta: new evidence, follow-up announcements, adoption, criticism, benchmarks, bugs, policy changes, community sentiment, or other meaningful changes.

Use attention proxies when exact search-volume data is unavailable, including breadth of independent coverage, follow-up reporting, Hacker News engagement, Reddit discussion, GitHub activity, engineering blog coverage, practitioner references, and credible social-media discussion. Never invent exact popularity or search-volume metrics.

---

# Session 1 — AI Industry & News Pulse

## Goal
Answer: **What AI news is receiving the most attention right now, and what does it tell us about the overall direction of the AI industry?**

Separate into:
- `## 국내 AI News`
- `## 해외 AI News`

Classify by where the event originates and who the primary subject is, not by publication language or publisher nationality. Samsung/NAVER/Kakao/Rebellions/FuriosaAI events are domestic; OpenAI/Anthropic/Google/NVIDIA/AMD/Microchip/Hailo events are overseas.

Prioritize high-attention developments such as mergers/acquisitions, IPOs, financing, investments, major product/model launches, security incidents, outages, regulation, legal disputes, strategic partnerships, infrastructure announcements, semiconductor events, and major competitive moves.

Rank the strongest stories first using available attention signals. Typically include about 5–8 domestic and 5–8 overseas stories, but use fewer when there are not enough strong items.

For each story include:
- **Summary:** 2–4 concise sentences
- **Why it is getting attention**
- **Industry implication**
- **Status:** Confirmed / Official claim / Independent report / Developing story / Rumor
- **Links:** 1–3 strong direct URLs, preferring primary sources plus reputable reporting

This session should be highly scannable and focused on industry awareness.

---

# Session 2 — AI Development Trend Radar

## Goal
Answer: **How is the way developers build software with AI changing, and what engineering practices are gaining or losing momentum?**

Actively search Korean and international practitioner sources, not only mainstream news. Use sources such as Hacker News, Lobsters, Reddit, GitHub Issues/Discussions/repositories, Korean developer communities, Korean technical blogs, engineering team blogs, practitioner newsletters, conference talks, substantive technical videos, credible X/social posts, and respected practitioners such as Simon Willison, Latent Space/swyx, Hamel Husain, Chip Huyen, Eugene Yan, and The Pragmatic Engineer. Discover additional high-quality sources dynamically.

Track broad AI-native software-engineering practices including:
- Harness Engineering
- Context Engineering
- Agent Orchestration
- Multi-agent / subagent workflows
- Agent runtime architecture
- Tool design and MCP workflows
- Sandboxing, permission models, guardrails
- Agent observability
- Eval-driven Development
- Specification-driven / documentation-driven development
- Long-running and parallel coding agents
- Worktree / branch-per-agent workflows
- Plan → implement → test → review pipelines
- Self-correction and test-feedback loops
- Human-in-the-loop patterns
- AI-assisted debugging/testing/code review/CI/CD
- Autonomous issue resolution
- Repository-level memory
- AGENTS.md / CLAUDE.md practices
- Prompt/runtime architecture
- LLM-as-a-judge / evaluator design
- Coding-agent benchmark methodology
- Local/on-device AI development
- AI-assisted architecture and system design
- Newly emerging AI-native engineering patterns

Do not bias this session toward PIM, firmware, embedded systems, or semiconductors. It should represent AI development as a whole.

For each meaningful trend explain:
- **What it is**
- **Problem it addresses**
- **How developers are using it**
- **What changed recently**
- **Evidence / limitations:** production cases, experiments, benchmarks, failures, criticism, counter-evidence
- **Trend direction:** growing / stabilizing / fragmenting / challenged / declining
- **Maturity:** Production practice / Emerging practice / Experiment / Community hypothesis
- **Sources:** useful primary and practitioner URLs

Continue to mention important trends across multiple days when they remain active. Track their evolution rather than repeating definitions.

---

# Session 3 — AI for Firmware & Embedded Engineering

## Goal
Answer: **How can current AI-development trends be applied to firmware and embedded engineering, and how are firmware/embedded developers actually using them?**

This session may overlap with Session 2, but all interpretation must be firmware-centric.

Search Korean and international embedded communities, blogs, GitHub repositories, technical write-ups, forums, and social discussions for real or technically plausible uses involving:
- Embedded C/C++ and MCU firmware coding agents
- HAL/driver generation or migration
- Register-level development
- Datasheet/reference-manual assisted development
- RTOS development/debugging
- Cross-compilation and build automation
- Flash/programming automation
- SWD/JTAG/UART tooling
- Serial-log analysis
- Hardware-in-the-loop agents
- Board farms and real-hardware regression testing
- Protocol testing/fuzzing
- Static analysis + AI
- Crash/log/root-cause analysis
- AI-assisted firmware CI
- Firmware AGENTS.md / CLAUDE.md
- MCP/tool interfaces for embedded tooling
- Hardware/software co-design
- Edge AI deployment
- Quantization and embedded inference optimization
- AI-assisted device validation

For relevant Session 2 trends, explicitly reinterpret them for firmware. Example: Harness Engineering may become `edit → cross-compile → flash → capture UART → hardware test → evaluate → retry`.

For each item include:
- **Firmware interpretation**
- **Practical workflow**
- **Useful tools / interfaces**
- **Benefits**
- **Limitations / risks** such as destructive flash operations, hardware damage, non-deterministic hardware, weak test oracles, limited simulation, or security boundaries
- **Evidence / maturity**
- **Sources**

Do not force a firmware interpretation when the connection is weak.

---

# Session 4 — AI Developer Tools Intelligence

## Goal
Answer: **What changed in major AI developer tools, how are they performing in practice, and what problems should developers know about today?**

Track:
- OpenAI Codex
- Claude Code
- Gemini CLI
- GitHub Copilot
- Cursor
- Windsurf
- Cline
- Aider
- Major open-source coding agents
- Emerging tools worth watching

Check both official and practitioner sources.

Official signals:
- Release notes / changelogs
- Official blogs/docs
- GitHub releases
- Pricing pages
- Status pages
- API/CLI docs

Practitioner signals:
- GitHub Issues/Discussions
- Hacker News
- Reddit
- Developer forums
- Social media
- Technical blogs
- Independent benchmarks
- User reports

Track meaningful changes involving versions, features, model changes, CLI/IDE/API/SDK changes, breaking changes, compatibility, pricing, rate limits, quotas, context limits, token/credit consumption, performance, regressions, bugs, crashes, outages, authentication, OS-specific issues, extension conflicts, reliability, security, and user sentiment.

For each meaningful update include:
- **Tool / version**
- **What changed**
- **Why it matters**
- **Official status / claim**
- **Developer feedback:** positive / negative / mixed / insufficient evidence
- **Known issues / regressions**
- **Usage / pricing implications**
- **Platforms affected**
- **What to watch**
- **Sources:** official URL plus practitioner URL when useful

Do not invent updates. For especially important tracked tools, `No material update found` is acceptable.

---

# Source & Verification Strategy
Prefer:
1. Primary sources: official announcements, docs, release notes, status pages, papers, GitHub releases, institutional announcements
2. Practitioner/community sources for trend detection and real-world experience
3. Reputable Korean and international journalism for broader context

Cross-check major claims whenever possible.

Clearly distinguish confirmed fact, official claim, independent reporting, practitioner experience, community sentiment, speculation, and rumor. Never present rumors, community claims, vendor benchmarks, or social-media speculation as confirmed fact.

For acquisitions, IPOs, financing, security incidents, outages, legal/regulatory events, and other high-impact news, prefer primary verification and multiple reputable reports.

---

# Output Format
Write in Korean while keeping company names, product/model names, APIs, protocols, libraries, frameworks, commands, and common technical terminology in English when appropriate.

Use clean Markdown:

# AI Daily Briefing — YYYY-MM-DD
> Search window: YYYY-MM-DD HH:MM KST → YYYY-MM-DD HH:MM KST

## Executive Summary
3–5 most important takeaways.

# Session 1 — AI Industry & News Pulse
## 국내 AI News
## 해외 AI News

# Session 2 — AI Development Trend Radar

# Session 3 — AI for Firmware & Embedded Engineering

# Session 4 — AI Developer Tools Intelligence

## Ongoing Topics to Watch
Persistent high-interest topics with the latest delta.

## Today’s Things to Check
1–3 concrete items worth reading, testing, or investigating.

Writing rules:
- Prefer signal over volume.
- Be concise but technically substantive.
- Avoid hype and clickbait.
- Do not manufacture a trend from one weak post.
- Do not confuse popularity with technical validity.
- Include criticism, failures, limitations, and counter-evidence where useful.
- Do not overstate vendor benchmarks.
- Preserve useful overlap across sessions when interpretation differs.
- Use direct source URLs wherever practical.
- Do not force weak content into empty subsections.
