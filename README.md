# The AI Stack I Actually Use

A working list of the tools I use to build with AI, run a family real estate business, and stay sharp as a marketer. Written by someone who can read Python at gunpoint but never trusted himself to ship anything serious until AI changed the equation.

## Read this first

Most "awesome AI" lists read like a LinkedIn post from someone trying to sound smart at a conference. Long. Comprehensive. Generic. Useless if you actually want to ship something on a Tuesday morning while your three year old throws Cheerios at your laptop.

This isn't that list.

I'm a marketer based in Israel. I have three kids. I have ADHD. I help run a family real estate business and I take on consulting work in marketing and AI. None of those things give me time to wrestle with tools that look great in a screenshot and fall apart the moment I ask them to do something real.

So this is an honest inventory. What's on my machine. What each tool earns its keep doing. What I'd skip if I were starting over.

If you're a senior engineer hunting for the latest niche MCP server, scroll to the bottom. The big lists will serve you better. But if you're a marketer, an operator, a founder, or a curious person who keeps reading "just build with AI" threads and thinking *but how though*, this is for you.

## How I pick tools

Every tool here had to pass three tests.

**It saves me at least 30 minutes a week, or it's gone.** I don't keep tools around because they're cool. I keep them because they made room in my week.

**I can connect it in under 20 minutes.** If the README is a wall of yak shaving, life is too short. I'm not hiring a developer to set up my note app.

**It plays nicely with the rest of the stack.** Tools that don't talk to anything else are just expensive bookmarks.

That's it. No vibes, no FOMO, no "but everyone's using it." If it doesn't move my week forward, I delete it.

## What I'm actually trying to do

So you can decide if my situation maps onto yours, here are the jobs I'm hiring this stack for.

**Inbox and calendar.** I'd rather not look at either. I want triage, drafts, prep notes, scheduling. I want them done before my second coffee.

**Writing.** Proposals, posts, replies, the occasional pitch deck. In English and Hebrew, both in my actual voice and not "as an AI language model" voice.

**Research.** Markets, competitors, leads, prospects, model releases, real estate comps. Fast, clean, with sources I can click.

**Family ops.** Kid school stuff, household paperwork, the chaos that piles up between weekday mornings.

**Learning.** The slow ongoing work of teaching myself how to build with AI so I can do everything above faster.

Every tool below earns its place by doing real work inside one of those buckets. If it doesn't, it's not here.

## Claude Desktop vs Claude Code

Quick orientation before the tool list, because where a tool runs matters and it confused me for weeks when I started.

**Claude Desktop** is the chat app for Mac and Windows. Most of the tools below plug into it through MCP servers, which you install one of three ways: through the settings UI for remote (HTTP) servers, by clicking install on a `.dxt` Desktop Extension, or by editing the `claude_desktop_config.json` file yourself for local STDIO servers. Once a tool is connected, it shows up inside your conversations.

**Claude Code** is the command line tool. It can do everything Claude Desktop can do, plus run scripts, install packages, edit files, clone any GitHub repository, and execute real commands on your machine. You install MCP servers in Claude Code with a single `claude mcp add` command. You can also clone any repo on GitHub and use it directly. There's no "is there a packaged installer for this" question.

The practical implication is this: if a tool exists only as a GitHub repository (not as a hosted MCP server or a packaged Desktop Extension), Claude Code can install and run it. Claude Desktop usually cannot, unless the maintainer has packaged it for you. The biggest community tools (Memory Service, Workspace MCP) provide both paths. Niche ones often don't. Knowing this saves you from chasing tools you can't actually run.

Skills work in both Claude Desktop and Claude Code. The Skills you build for one will run in the other. This wasn't true a few months ago and it's a meaningful change for non developers in particular.

How I use them: when I'm building or wiring things up, I'm in Claude Code. When I'm working (drafting, reviewing, thinking, dealing with email), I'm in Claude Desktop. Most days I have both open.

## The core stack (start here)

Three things. Install these in this order and don't read further until you've used them for a week.

### Claude Desktop

Anthropic's actual app for Mac and Windows. The cockpit. You'll spend 80% of your time here.

If you only have an hour today, spend it just chatting. Get a feel for how Claude thinks. The rest of the stack starts to make sense once you've used the cockpit.

[Download Claude](https://claude.com/download)

### Claude Code

The command line tool that turns Claude into an agent that can read and write files on your computer, run scripts, install packages, and clone repos. Yes, it lives in the terminal. Yes, that feels alien if you've spent your career inside design tools and a browser.

Push through it anyway. Two evenings of frustration buys you years of compounding productivity. This is the single biggest jump in capability you can make as a non developer. The first time Claude Code installs and configures a new tool for you while you watch, something clicks and you don't go back.

[Claude Code docs](https://code.claude.com/docs/en/overview)

### The reference MCP servers

Anthropic maintains a small set of official open source MCP servers. Fetch, filesystem, memory, git, sequential thinking. These are the "hello world" of the MCP ecosystem. Install fetch and filesystem on day one. The rest you can add as you need them.

[Official MCP servers repo](https://github.com/modelcontextprotocol/servers)

That's the foundation. Skills get their own section next because they deserve it.

## Skills (the second multiplier)

If MCP servers are how you give Claude new capabilities, Skills are how you teach Claude how to use them well. Think of each Skill as a small expert with specific instructions, examples, and resources, loaded only when the work calls for it. Anthropic introduced them in late 2025. They're the second biggest jump in productivity I've made, after MCP itself.

I run a few Skills regularly. The ones I reach for most:

- A custom role-evaluation Skill (one I wrote from scratch as a SKILL.md) that scores opportunities against fixed fit criteria and generates tailored documents from structured inputs
- A marketing-copy Skill that enforces my voice rules: no em dashes, a banned-word list including "leverage", "seamless", and "robust", and a bottom-line-first cadence
- An inbox-triage Skill that routes by sender type (clients, family, vendors, newsletters), drafts in the right language, and flags anything that needs me today before 8:30am
- A weekly-planning Skill that respects how my week shapes up (full-capacity, half-capacity, and kid days) and refuses to schedule deep work on the wrong day
- Channel-specific Skills for LinkedIn first-line hooks, X thread structure, and email follow-up cadence

Customizing the official skills is underrated. The ones Anthropic ships are great starting points but they're designed for general audiences. Spend twenty minutes adjusting one to your actual context and it becomes twice as useful. Spend an hour and it becomes indispensable.

### The official starting points

[anthropics/skills](https://github.com/anthropics/skills). Anthropic's official skills repository. Start here. Clone it, look at how the skills are structured, copy one, modify it. The fastest way to learn the format.

[agentskills.io](https://agentskills.io). The open standard for the Skills format. Worth knowing about if you ever want to publish skills that work across Claude, Codex, Gemini CLI, Cursor, and the other tools that have adopted the spec.

### Where to find skills built by others

[ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills). Actively maintained, well organized, updates often.

[travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills). One of the bigger general purpose lists.

[karanb192/awesome-claude-skills](https://github.com/karanb192/awesome-claude-skills). 50+ verified skills, focused on quality over volume.

[VoltAgent/awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills). 1000+ skills across every tool that implements the agent skills format. Browse with intent, not for inspiration.

[obra/superpowers](https://github.com/obra/superpowers). 20+ battle tested skills for Claude Code (TDD, debugging, collaboration patterns). Developer leaning.

[hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code). Claude Code specific. Skills, hooks, slash commands, plugins all in one place.

Honest take: don't try to install fifty skills at once. Pick three or four that fit work you actually do. Use them for a week. Notice which ones you reach for. Then add more.

## Email, calendar, and inbox stuff

If you only tackle one section on this list, tackle this one. Email is where most of us bleed time, and where AI gives the fastest, most visible wins.

### Google Workspace MCP (taylor-wilsdon)

A community built MCP that gives Claude access to Gmail, Calendar, Drive, Docs, and Sheets in one package. Distributed as a `.dxt` Desktop Extension, which means one click install on Claude Desktop. Replaces three separate Google MCPs with one cleaner setup.

What I use it for: morning inbox triage, calendar prep before client calls, pulling up the right Drive doc without context switching, sweeping for follow ups I forgot about.

[taylorwilsdon/google_workspace_mcp](https://github.com/taylorwilsdon/google_workspace_mcp)

### Gmail MCP (official)

Anthropic's remote Gmail MCP. Simpler and more limited than the community Workspace MCP above. Fine if you just want to read and search emails. The Workspace MCP is better if you want to actually take action on them.

### Google Calendar MCP (official)

Lets Claude see your calendar, suggest times, draft events. Annoyingly basic for now. Still saves me from the worst scheduling threads.

### Honest take

Google's official MCPs are improving fast but the community Workspace MCP is still better for most workflows. Use that as your default. Run the official ones in parallel only if you need a specific feature.

## Notes, docs, and knowledge

### Notion MCP (official)

If Notion is your second brain, this is non negotiable. Search, read, and update pages and databases from inside Claude. I use it constantly. Pulling client briefs. Updating project status pages. Dumping research into the right database without leaving the conversation.

[Official Notion MCP](https://www.notion.com/help/notion-mcp)

### Google Drive MCP (official)

Search and fetch Drive files. Combines well with the Gmail MCP for "find that PDF Avi sent in October" type queries. Boring but essential.

### Filesystem MCP (official)

Read and write local files. The most underrated tool on this entire list. This is what makes Claude useful for actual work and not just chat. Once Claude can touch your files, the whole game changes.

## Memory and persistent context

The single most underrated category in the AI stack. If you take nothing else from this list, take this section. Memory is the difference between a clever chatbot and a tool that feels like it knows you.

### MCP Memory Service (doobidoo)

Persistent memory for Claude. Stores facts, decisions, preferences, and context across every conversation, on every machine, forever. I run it with a Cloudflare D1 and Vectorize backend so my memory follows me from laptop to laptop without missing a beat.

What it actually does: Claude knows who my kids are. Knows what projects I'm working on. Knows what my writing voice sounds like. Knows what tools I prefer, what I've already tried, what I've decided and why. I never re explain anything. I just keep working.

This is the highest leverage piece of software in my entire stack. Set it up on day one even if you don't fully understand why yet. You'll get it within a week.

[doobidoo/mcp-memory-service](https://github.com/doobidoo/mcp-memory-service)

### Context7 MCP

Live, version specific documentation for hundreds of libraries pulled into Claude's context on demand. Add `use context7` to any coding prompt and Claude stops inventing API methods that don't exist. Essential the moment you start writing or even copy pasting code.

[Context7](https://context7.com)

### Sequential Thinking MCP

Forces Claude into structured reasoning steps. Useful for big decisions, complicated planning, or when you can tell Claude is being sloppy and you want it to slow down. I use it less than I should.

## Web research and content

### Fetch MCP (official)

Pull any URL into Claude as clean markdown. The most boring MCP on this list. Also one of the most useful. I use it for everything. Reading articles. Scraping competitor landing pages. Pulling product spec sheets. Researching companies before applying. Sniffing out what a potential client actually does.

### open-webSearch

Free web search across Bing, DuckDuckGo, Baidu, and others, no API keys required. A solid fallback when you don't want to spend money on a paid search MCP. Results are sometimes weaker than the paid options but for general "what's the latest on X" it's perfectly fine.

[Aas-ee/open-webSearch](https://github.com/Aas-ee/open-webSearch)

### Brave Search MCP

Paid but high quality search results. Worth the cost if you do serious research.

### Apify Actors MCP

Access to 3,000+ pre built web scrapers. This is where it gets fun for marketers. Competitor research, lead generation, content harvesting, social listening, all from inside Claude. Steeper learning curve than the others. The payoff is huge if you do any kind of audience or competitive intelligence work.

[Apify Actors MCP Server](https://github.com/apify/apify-mcp-server)

## Workflow automation (no code or low code)

The bridge between Claude and the rest of your stack. This is where you turn one off magic moments into systems that run without you.

### Make.com MCP

Official MCP for Make (formerly Integromat). Lets Claude design, trigger, and manage Make scenarios. This is the no code person's gateway drug. I use Make for anything that needs to fire on a schedule or react to an event. Inbox watchers. Document handovers. Slack notifications when something hits a Notion database. The boring stuff that adds up.

The pattern I run: Claude designs the logic in plain language, I build it visually in Make, Claude can later trigger or modify it. Best of both worlds.

[Make.com MCP](https://help.make.com/make-mcp-server)

### Pipedream

2,500+ APIs and 8,000+ prebuilt tools. More powerful than Make. Also more complex. I haven't fully committed to it but I respect what it can do, and if I ever outgrow Make this is where I'd land.

[PipedreamHQ/pipedream](https://github.com/PipedreamHQ/pipedream)

### Zapier MCP

If you already live in Zapier, the MCP exposes your existing Zaps to Claude. Probably not worth migrating to Zapier just for this. If you're already there, plug it in.

## Communication

### Slack MCP (official)

Read, post, search Slack messages and channels. If your work happens in Slack, essential. If it doesn't, skip.

[Official Slack MCP](https://slack.com/help/articles/48855576908307-Guide-to-the-Slack-MCP-server)

## Power user stuff

The heavier tools. Don't install these on day one. Come back after you've run the basics for a month.

### Windows-MCP (CursorTouch)

Lets Claude control your Windows desktop. Mouse, keyboard, windows, processes. Powerful and slightly terrifying. Start with a limited scope until you trust it. I use it sparingly for repetitive tasks that don't have an API. Excellent for those legacy desktop apps that haven't seen a developer since 2014.

[CursorTouch/Windows-MCP](https://github.com/CursorTouch/Windows-MCP)

### Claude in Chrome

A Chrome extension that turns Claude into a browser agent driving your actual browser, not a headless one. Still in beta. Worth trying once you have a use case that goes beyond what Fetch can handle.

[Claude for Chrome](https://claude.com/blog/claude-for-chrome)

### Playwright MCP

Headless browser automation. For repeatable scraping, testing, or any browser flow you want to script. More developer leaning than the rest of this list but powerful once you've got the basics down.

[Microsoft Playwright MCP](https://github.com/microsoft/playwright-mcp)

## Documents and PDFs

If you work with contracts, reports, or any kind of paperwork, this is your category. Most office workers underestimate how much of their week is just wrestling with PDFs.

### PDF MCP servers

Multiple options for reading, filling, extracting, and annotating PDFs. Useful for anyone in real estate, legal, finance, or anywhere paper still rules. They save me hours every week.

### pdf-viewer MCP

An interactive PDF viewer with annotation, highlighting, and form filling. Different from the read only PDF tools. The one to reach for when you actually need to do something with the document, not just read it.

## Stack recipes

The point of MCP is that tools compose. These are workflows I actually run, with rough time savings.

### Recipe 1: The morning sweep

**Time:** 15 to 20 minutes. Down from 90.
**Stack:** Workspace MCP, MCP Memory Service, Claude Desktop.

I sit down with coffee. I ask Claude to review my inbox, surface anything that needs me today, draft replies in the right language (most clients in English, family stuff in Hebrew), and check my calendar for the next 24 hours. Because of the Memory Service, Claude already knows which client is which, which family member handles what, and what tone to use with each. I review, edit lightly, hit send. The inbox closes by 8:30am.

The first time I ran this end to end I almost cried at how much time it saved.

### Recipe 2: Idea to LinkedIn post

**Time:** 30 minutes.
**Stack:** Fetch, open-webSearch, MCP Memory Service.

I drop a thought into Claude. It searches the web for current context, fetches the most relevant sources in full, then drafts a post in my actual voice (the Memory Service has my voice and style baked in from a year of conversations). I edit, post. Half an hour, start to finish. Without this, I'd stare at a blank LinkedIn editor for two hours and then give up.

### Recipe 3: From idea to running automation

**Time:** An afternoon to design and build. Then minutes to trigger.
**Stack:** Make MCP, Claude Code.

Most useful when I have a workflow I want to automate but I'm not sure how. I describe the goal in plain language. Claude walks me through what triggers, what data, what destinations. We sketch the scenario together. I build it visually in Make. From then on, Claude can trigger or modify the scenario whenever I need it.

This pattern killed off about ten of my "I should automate this someday" mental tabs in a single afternoon.

## Personalization (the unsexy thing nobody talks about)

This is the section that should be twice as long as it is, because almost no one does it and almost everyone needs it.

Out of the box, Claude is a smart generalist. Useful, but it doesn't know who you are, what you're doing, how you make decisions, how you communicate, or what kinds of mistakes you tend to make. By default, it will give you the same kind of help it gives everyone else.

You can change that. Both Claude Desktop and Claude Code let you give Claude persistent context about yourself, your preferences, and your goals. Spend an hour on this once and every conversation afterward gets sharper.

Here's what I configured.

**Who I am.** Background, family situation, location, the work I do. So Claude doesn't write to me like I'm a Silicon Valley founder when I'm a marketer in Israel running a family business.

**What I'm trying to do right now.** Active projects, the role I'm exploring, what I'm building, what I'm learning. So when I ask something, Claude has the context to make it relevant instead of generic.

**How I make decisions.** I want help prioritized by leverage, urgency, feasibility, downside risk, and return on time. Not "here are six options, what do you think?" Give me a recommendation. Then the alternatives.

**How I want responses.** Concise by default. Bottom line first. One recommended next step before the plan. Direct, blunt, willing to push back on my thinking, not just agree with me. Encouraging as a person, critical as an analyst. This sounds obvious. It is not what happens by default.

**My ADHD.** This is the biggest one. I told Claude to:

- Break things into small actionable steps
- Add a realistic time estimate to anything execution oriented
- Warn me explicitly when something looks like a rabbit hole, before going deep
- Simplify when I'm overcomplicating
- Recap where we are when I return to a topic after a gap
- Default to small incremental progress over ambitious plans that won't survive contact with a kid day

This setup has done more for my output than any single tool on this list. It's the difference between Claude as a clever chatbot and Claude as something that protects me from myself. I'm naturally curious. I get pulled into rabbit holes that have nothing to do with what I should be doing. Having Claude flag it before I go in ("heads up, this looks like a divergence from your actual goal, do you want to go deep or stay on track?") has saved me dozens of hours.

**Language.** English by default. Hebrew when I'm drafting something that needs to be in Hebrew. Don't translate culture, just words.

How to set this up:

For Claude Desktop, look for "user preferences" in settings. Write what matters in plain language. Update it as you learn what Claude needs to know.

For Claude Code, create a CLAUDE.md file at the user level. Anything in there persists across every session. The simplest approach: write what you'd tell a smart new colleague about how to work with you on day one.

Don't try to make this perfect on the first pass. Mine has gone through about ten revisions. Each one made the conversations after it noticeably better.

## Things I tried and dropped

Honest section. Not everything earns a permanent spot.

### Auto-GPT and AgentGPT

Tried them when the hype was loud. Too unreliable for real work. Claude Code does the same job better and doesn't randomly spend $40 of OpenAI credits while you're making lunch.

### Multiple "second brain" apps

I went through Roam, Obsidian, Logseq, Reflect, and Mem. Eventually I realized the answer wasn't a better note app. It was Notion plus the Memory Service. Notion holds structured stuff. Memory holds context. Done. I stopped chasing the perfect note system around the same time I stopped chasing perfect productivity systems generally, which is to say when I had my third kid.

### Heavy multi agent frameworks

Tried a few of the orchestration frameworks that promise teams of cooperating agents working together. Cool to read about. Wildly overkill for what most non developers actually need today. Maybe one day. Not now.

### Anything that requires running Docker just to try it

I can run Docker. I just don't enjoy running Docker. If a tool's only install path is "spin up a container," I'll usually find another tool. Life is short and my disk space is shorter.

## A few notes for non developers

Worth being honest about my own starting point.

I'm not a developer and I never have been. But I'm not totally green either. Over the years I've poked around in Python and SQL the way a curious marketer does. Reading Stack Overflow at 11pm. Copying recipes from documentation. Making something work for a specific use case and then breaking it the moment I tried to extend it. Calling a friend who actually writes code for a living whenever something serious went wrong. He'd patiently explain what I'd misunderstood. I'd nod. Then I'd hit the next wall a few weeks later and call again.

AI changed that. Completely.

I still don't write code from scratch the way an engineer does. But the gap between "I have an idea" and "I have a working version" has collapsed. I can install repos I would have been afraid to touch a year ago. I can read an error message, paste it into Claude, and actually understand what comes back. I can wire up systems that used to require a development team.

That's the real story of this whole stack. Not the individual tools. The fact that someone like me can now build serious workflows alone, in evenings, between bedtime stories and the morning school run. I don't have to call my coder friend anymore. I just keep working.

A few things that helped me get there:

**Treat the terminal as just another text input.** If you've never used it, it looks alien. It's not. You type something, hit enter, you read what comes back. That's the whole thing.

**Lean on Claude Code to install stuff.** When a README says "clone this repo and run these commands," paste the README into Claude Code and ask it to do it for you. Watch what happens. Learn from that. This was the biggest single unlock for me.

**Don't try to understand everything before you start.** Install the thing. Use it for a day. Read about how it works after you've felt the value. The "study first, use later" instinct will keep you reading articles forever and shipping nothing.

**Build your own Skills early.** Even one Skill saves you so much repetitive prompting that you'll wonder how you survived without them. Start with whatever task you do most often. Mine was inbox triage.

**Accept that you're going to feel stupid for the first two weeks.** Everyone does. The people who get good are the ones who keep showing up anyway.

## On my radar

Things I'm planning to try, in rough order of priority.

**Cognee MCP.** Graph based memory. Might be more powerful than vector memory for relational data, like a marketing CRM where every contact, company, deal, and email connects to several others.

**Linear MCP.** If I ever move project management out of Notion. Currently happy where I am.

**HubSpot MCP.** For when I'm doing serious marketing or CRM work, either for myself or for a client.

**Figma MCP.** Design context inside Claude. Useful even if you only brief designers and never open Figma yourself.

**More custom Skills.** Specifically a real estate negotiation skill, a client onboarding skill, and a content repurposing skill. The skill backlog is longer than the time I have.

## Bigger lists if you want the firehose

For MCP servers, once you've got a working stack, these are the places to go for breadth:

[wong2/awesome-mcp-servers](https://github.com/wong2/awesome-mcp-servers). The big one.

[punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers). Also huge.

[appcypher/awesome-mcp-servers](https://github.com/appcypher/awesome-mcp-servers). Well organized.

[tolkonepiu/best-of-mcp-servers](https://github.com/tolkonepiu/best-of-mcp-servers). Ranked by an automated quality score.

These lists have ten times the breadth of what I've written. They also have ten times the noise. Use them when you have a specific need ("I want something that does X"), not as a starting point. Starting point lists with 400 items are how you end up reading about AI tools for three hours instead of using one.

## What this list isn't

A complete catalog. A guide for engineers. A statement of which tools are objectively best.

It's a snapshot of what's actually working for me right now, written for people who don't have time to read another 500 item awesome list.

If you have a tool you swear by that fits how I think about this stuff, open an issue or send me a note. I update this whenever something earns a spot, or loses one.

---

Built by Jonathan Winkler. Marketer, AI consultant, father of three. Based in Ra'anana, Israel.

Last updated May 2026.
