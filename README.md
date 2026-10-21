building myself & cool things under [pragnya](https://pragnyaa.in) :)

a little over a year of shipping production software, and most of the rest of my time goes into systems i build for myself. mostly typescript: react, next.js, node, postgres.

---

## projects

### ai & systems

**edward** ([demo](https://youtu.be/zIBuOmr92_s) / [github](https://github.com/pragnya-works/edward) / [writeup](https://blog.shubhojeet.com/edward))

a prompt-to-production app platform i built solo: you describe an app, an agent writes the code, runs it in a sandbox, and hands back a preview url. the interesting part is not the model, it is the runtime around it - postgres advisory locks for run admission, an append-only event log so runs survive worker crashes and browsers replay from their last event id, bullmq workers, a network-isolated docker sandbox per chat, and a build worker that turns generated files into a routed url. the tradeoff: every stream event is a postgres write. replay and recovery become easy, but the database does real work on every run.

**agentic chat** ([live](https://agentic.shubhojeet.com) / [github](https://github.com/shubho0908/agentic-chat))

a 0-1 agent chat product: a langgraph agent loop with postgres checkpointing, pgvector hybrid search with cohere rerank, and human approval gates before any connector mutation, wrapped in ssrf and prompt-injection guardrails. the approval gates slow the happy path down on purpose - an agent that can act on your accounts should have to ask first.

### developer tools & infrastructure

**fieldcraft** ([live](https://fieldcraft.shubhojeet.me) / [github](https://github.com/shubho0908/fieldcraft))

a chrome mv3 side-panel extension that parses the page you are on, looks companies up locally, and fills forms only after you approve each field. zero telemetry. keeping everything local means no server to run and nothing to leak, but the company data ships with the extension instead of staying live.

**deployninja** ([demo](https://youtu.be/-E-A0wyCeeE) / [github](https://github.com/shubho0908/deployninja))

a github-triggered deployment pipeline: docker builds pushed to ecr, real-time build logs through kafka into clickhouse, rolling updates on ecs. built for my own apps on one aws account - a personal pipeline, not a multi-tenant platform.

### media & workspaces

**inkdown** ([live](https://inkdown.shubhojeet.com) / [github](https://github.com/shubho0908/inkdown))

a markdown workspace: folder hierarchies with recursive postgres ctes, a scroll-synced editor preview, cloudflare r2 for storage.

**intellect ai** ([demo](https://youtu.be/QKx_BKJQ9tw) / [github](https://github.com/shubho0908/intellect-ai))

an async image and video generation pipeline: worker polling across replicate models, mongodb queues, cdn caching.

**video platform** ([demo](https://youtu.be/CJEoNpLgRRw) / [github](https://github.com/shubho0908/youtube-clone-mern))

an early build, kept public because the upload architecture is still worth reading: 100mb chunked resumable uploads, firebase storage, and mongodb engagement trees.

---

## writing

i write up whatever i learn & how these systems actually work at [shubho's blog](https://blog.shubhojeet.com).

---

<p align="left">
  <a href="https://shubhojeet.com" target="_blank" rel="noreferrer" title="website"><picture><source media="(prefers-color-scheme: dark)" srcset="https://img.icons8.com/ios/50/e4e4e7/globe--v1.png"><source media="(prefers-color-scheme: light)" srcset="https://img.icons8.com/ios/50/27272a/globe--v1.png"><img src="https://img.icons8.com/ios/50/71717a/globe--v1.png" width="20" height="20" alt="website" /></picture></a>
  &nbsp;&nbsp;&nbsp;
  <a href="https://blog.shubhojeet.com" target="_blank" rel="noreferrer" title="blog"><picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/rss/e4e4e7"><source media="(prefers-color-scheme: light)" srcset="https://cdn.simpleicons.org/rss/27272a"><img src="https://cdn.simpleicons.org/rss/71717a" width="20" height="20" alt="blog" /></picture></a>
  &nbsp;&nbsp;&nbsp;
  <a href="https://x.com/shubhojs" target="_blank" rel="noreferrer" title="x"><picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/x/e4e4e7"><source media="(prefers-color-scheme: light)" srcset="https://cdn.simpleicons.org/x/27272a"><img src="https://cdn.simpleicons.org/x/71717a" width="19" height="19" alt="x" /></picture></a>
  &nbsp;&nbsp;&nbsp;
  <a href="https://www.linkedin.com/in/shubhobera" target="_blank" rel="noreferrer" title="linkedin"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" width="19" height="19" alt="linkedin" /></a>
  &nbsp;&nbsp;&nbsp;
  <a href="https://youtube.com/@shubhojeetbera" target="_blank" rel="noreferrer" title="youtube"><picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/youtube/e4e4e7"><source media="(prefers-color-scheme: light)" srcset="https://cdn.simpleicons.org/youtube/27272a"><img src="https://cdn.simpleicons.org/youtube/71717a" width="21" height="21" alt="youtube" /></picture></a>
  &nbsp;&nbsp;&nbsp;
  <a href="mailto:hey@shubhojeet.com" title="email"><picture><source media="(prefers-color-scheme: dark)" srcset="https://img.icons8.com/ios/50/e4e4e7/mail--v1.png"><source media="(prefers-color-scheme: light)" srcset="https://img.icons8.com/ios/50/27272a/mail--v1.png"><img src="https://img.icons8.com/ios/50/71717a/mail--v1.png" width="20" height="20" alt="email" /></picture></a>
</p>
