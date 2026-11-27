---
agent: cl-6.customers@PrompTugal.dinis
written: 2026-11-27T00:53Z
brief: 2026-11-27-competitive-analysis-and-the-research-on-the-home-page.md (brief 7)
inputs: cl-6.researcher's parts A and B (https://github.com/PrompTugal/PrompTugal__Agent__Researcher/blob/dev/site/factory/dinis-cruz/account-f/findings/2026-11-27-competitive-analysis-a-and-b.md, commit fa36228, 13 sites read 27 Nov 2026); our own repository PrompTugal/PrompTugal__News__Website, branch dev, commit 7738a4d83 (27 Nov 2026, 00:39 UTC), read at 2026-11-27T00:53Z
state: draft for Dinis, via cl-6.conductor; nothing built; cl-6.security to see it before any site changes
---
# Part C: what we learn, and a home page that shows the research

## 1. What we learn from the 13 sites (each from researcher's rows, read 27 Nov)

1. **Method and corrections are one click from the front page** on the research-led sites (ProPublica, The Markup, Full Fact, Bellingcat, Texas Tribune). Readers trust what they can check.
2. **The best "show the work" device pairs a story with its method** (The Markup's "How we investigated": what was asked, of how many sources, how many refused).
3. **Only Our World in Data leads with volume** (14,158 charts, 39 explorers). No site read shows sources per story on its home page. That is open ground for us.
4. **Full Fact shows its own AI work in the main navigation;** Bellingcat publishes AI how-tos. Being open about AI is a strength where trust is the product.
5. **The Portuguese sites show who is behind the paper** (ficha tecnica, estatuto editorial) but not method or corrections on the home page. Doing both would set us apart at home.
6. **Gaps in this evidence:** no screenshots, no article pages, Ground News and Semafor on About pages only, and no Portuguese data-led newsroom found. Treat the lessons as a start, not a survey.

## 2. Our superpower, in numbers from our own data

Every figure below is read from our repository (dev, commit 7738a4d83, 27 Nov 2026) and is the count of files or rows named, nothing estimated.

| What | Number | Where it comes from |
|---|---|---|
| Signed articles | 117 (all dated 5 to 26 Nov 2026) | `content/articles/*.md` with a `.sig` each in `articles/` |
| Places live, each with its own agent | 36 (1 country, 1 region, 16 municipalities, 18 cities) | `data/by-place/*.json`, status `live` |
| Local news items across those places | 317 | `ai_news` in each place file |
| Sources listed across those places | 506 | `sources` in each place file |
| Events listed across those places | 113 | `events` in each place file |
| Places updated on the latest day | all 36, on 26 Nov 2026 | `updated` and `latest_news.read_at` in each place file |
| Story projects | 149 | `data/stories/*/story.json` |
| Per-source records (publisher, date published, date we read it, who read it, what it says) | 133 | `data/stories/*/sources/*.json` |
| Companies, people, events as data | 120, 285, 248 folders | `data/companies`, `data/people`, `data/events` |
| Corrections and removals | 0 so far (the file is empty by design) | `data/corrections/`, `data/by-place/removals.json` |

**Honest limits.** The 133 source records sit in only 21 of the 149 story projects, so "sources per story" cannot be shown for every story yet; the home page should show it only where it exists, and the data gap is itself a task for cl-6.ontologist and cl-6.dev. "0 corrections" is true and should be shown with its meaning, not as a boast. I read the repository, not the live home page, so what readers see today is not checked here.

## 3. The proposal, against Dinis's four requirements and the research

Dinis's words are in the brief. His point: the amount and quality of research is not easy to see or understand today.

1. **More images at the top.** A wide image band of the places and stories, each image credited and linked to its story. Images only where the licence is clear (R12); cl-6.designer picks and cl-6.security checks licences.
2. **The map shows how many stories each place has, not region names.** Each of the 36 places drawn as a circle sized by its count (for example Faro 28, Portugal 22, Algarve 19, Porto 15 local news items today), the number printed on it, with the date it was last updated. Tapping goes to the place page. Same figures as the iOS app, from `data/by-place/`.
3. **Visibly fresh news.** A line on the front page that says when each part was last read ("36 of 36 places read on 26 Nov 2026"), from the files' own dates, and a latest-first list that the build refreshes. If a part is stale (older than about 13 hours, as the twice-a-day rule treats it), the line says so rather than hiding it.
4. **Local flowing up to regional and national.** A graph with local places at the bottom, the Algarve and other regions in the middle, Portugal at the top; items rise through it, by date, and the points where local items meet regional or national ones are marked. Views: a tree, a layered graph, and an optional 3D view, with a date slider. The structure already exists: `parent` links in `data/by-place/` (municipality to Algarve to Portugal) and `data/by-place/connections.json`; cl-6.ontologist shapes the local, regional, national data, cl-6.designer the design, cl-6.dev the build.
5. **A "How much we read" band** (the research made visible, in the style the research suggests): four to six counters from the table above, each linking to where it comes from, beside a one-line statement of method ("every fact sourced and dated, with the date we read it", already on the page) and links to corrections, how we check, and who the agents are. Our World in Data leads with volume; The Markup pairs story and method; Full Fact shows its AI. We can do all three.
6. **Per lead story, a "behind this story" strip:** sources read, date read, who read them, checks passed; shown only where the data exists, so it does not claim what is not there.
7. **A "how we investigated" page template** for a few flagship stories (the Markup pattern), starting with one we choose together.

## 4. Order and owners

| Step | Owner | Needs |
|---|---|---|
| Choose images and licences | cl-6.designer, cl-6.security | image sources with clear licences |
| Map as counts | cl-6.designer, cl-6.dev | the 36 place files (exist) |
| Freshness line | cl-6.dev | the dates (exist) |
| Local to national graph | cl-6.ontologist, cl-6.designer, cl-6.dev | parent links (exist), date per item |
| "How much we read" band and strips | cl-6.designer, cl-6.dev, cl-6.ontologist | source records on more stories (21 of 149 today) |

Nothing is built by me. For Dinis, through the conductor: the order, the images, and whether the graph's 3D view is wanted first.
