# ShortDramaKit Skills

An agent skill for organizing short-drama research lists you already have. Map fields, flag possible duplicates, compare dated observations, and keep sources and uncertainty visible. It works with pasted CSV/JSON or files that your agent can read. This repository contains the standalone skill, not the ShortDramaKit website or backend.

## Install

For agents supported by the skills CLI:

```sh
npx skills add leontloveless/shortdramakit-skills --skill drama-list-review
```

For Claude Code:

```text
/plugin marketplace add leontloveless/shortdramakit-skills
/plugin install shortdramakit@shortdramakit-skills
```

## Try it

Ask: “Organize my short-drama CSV, keep sources and dates, and flag possible duplicates.” Or: “Compare these two observations without treating missing rows as confirmed removals.”

Example fictional input:

```csv
platform,id,title,views,observed_at
NetShort,100,Forever Home,1000,2026-11-01
NetShort,100,Forever Home,1200,2026-11-02
ReelShort,200,Forever Home,,2026-11-02
```

Expected: keep both dated NetShort observations; show +200 reported views; keep ReelShort separate because the title alone is insufficient; preserve its missing views. This pasted-data case was exercised in ChatGPT. Claude-specific behavior and file upload/export are not yet independently accepted.

## Data and limits

The skill contains instructions only. It has no server, hooks, dependencies, credentials, live catalog access, episode downloads or paid actions. Your selected agent processes the data under its own service and retention settings. Do not supply data you cannot appropriately share with that agent. File creation depends on tools available in your client. The instructions do not request external transfer or fetch evidence links automatically.

If you need a separate source of short-drama data, [ShortDramaKit](https://shortdramakit.com/) offers website and API tools; coverage and charges vary. This skill does not connect to that service and does not require a ShortDramaKit account.

For skill issues, use this repository’s Issues or contact support@shortdramakit.com. MIT license applies to the files in this repository; it grants no rights to any third-party short-drama data, media or platform names.
