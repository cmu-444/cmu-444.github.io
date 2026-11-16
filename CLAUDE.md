# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

The public course website for CMU 17-444, "Production Machine Learning Systems for Software Engineers" (CMU Qatar, first offered Spring 2027). It's a static **MkDocs** + **Material for MkDocs** site. There's no application code: content is Markdown plus YAML data rendered through Jinja. It was bootstrapped from the 17-313 site, and the 17-313 content was removed. The site is intentionally bare-bones (Home with This Week + tentative weekly schedule, and Course Overview). It deliberately keeps the 17-313 look and homepage layout (the original source is at `~/Dropbox/cmu-se/f26/CMU-17313Q.github.io`); keep new work consistent with it. The syllabus, assignments, project, and labs are still to come; placeholders are commented out in `mkdocs.yml` `nav`.

The GitHub repo is `cmu-444/cmu-444.github.io` (moved from `cmu-prodml`), so it publishes as an organization site at the root, https://cmu-444.github.io/ (see `site_url`). Still prefer **relative** links and image paths (`assets/images/...`) so the site also works from `mkdocs serve`, previews, or a future move.

## Commands

```sh
pip install -r requirements.txt
mkdocs serve    # http://localhost:8000/
mkdocs build    # outputs site/ (never edit by hand)
cd docs/_data && python3 update_this_week.py   # regenerate this_week.yaml
```

There are no tests or linters. Verification means `mkdocs build` finishes with **no warnings** (it currently does) and the pages render correctly. Check light and dark mode, and narrow widths.

## Architecture

- The `markdownextradata` plugin exposes every `docs/_data/<name>.yaml` as `extra.<name>` in page Jinja. `docs/index.md` renders the **This Week** cards from `extra.this_week`, the full **Weekly Schedule** table from `extra.schedule`, and the staff cards from `extra.staff`.
- `docs/_data/schedule.yaml` is the hand-edited source of truth. It has one entry per class weekday (**Sun–Thu**, Qatar). The table's weekly separators assume exactly 5 rows per week (CSS `nth-child(10n+5)`/`(10n)`), so keep every weekday even when it's empty. Each entry has `date` (`"Ddd Mon D"`, no year), `type` (`Lecture` | `Lab` | `Exam` | `No class` | `''`), and the sub-objects `lecture`, `reading` (pre-lecture reading), `lab` (`name`, `slides`, `handout`; lab sessions go here and `lecture.name` stays empty on lab days; this replaced 17-313's `recitation`), `problemset` (problem sets/quizzes), `assignment` (individual assignments I*), and `homework` (project milestones M*). `assignment` and `homework` share the "Assignments & Project" column and This Week card, so a day can show both. `numDays` on `homework`/`problemset` is the table rowspan and how many business days the item stays in This Week. Unused fields are `''`, never omitted. The data was converted from `resources/S27 Course Schedule - Schedule - Spring 2027v1.csv`, (assignments and milestones: I1, I2, M1, M2 only). Planning remarks such as "(suggested…)" are internal and are not shown on the site. Its 17-445 source/reuse columns are internal planning notes and must not be published.
- `docs/_data/this_week.yaml` is **generated, don't hand-edit**. `update_this_week.py` (run from inside `docs/_data/`) derives it from `schedule.yaml` + `teamsurveys.yaml`. Dates get the *current* year (`strptime` ignores the weekday name), so This Week stays empty until January 2027. To preview it, run the script with `datetime.now` patched to a semester date, then restore the file.
- `docs/_data/teamsurveys.yaml` is currently `[]`. Entries use the 17-313 format (`opendate`, `closedate`, `deadline`, `name`, `link`). An empty `link` shows "Not opened yet!".
- CI (`.github/workflows/`, copied from 17-313): `update.yml` runs daily and on push to `main`. It regenerates `this_week.yaml`, auto-commits "Update weekly schedule", and calls `deploy.yml` (`mkdocs gh-deploy --force` to `gh-pages`).
- Theme: Material `primary: red` with the original 17-313 `docs/stylesheets/custom.css` (cards, labels, schedule table). The header uses `17444_logo_white.png` (the red logo vanishes on the red bar). The favicon was made from `resources/17-444-logo*.png` with ImageMagick. `overrides/main.html` loads Material Symbols (card icons) and sets the footer.
- `resources/` holds source material (course description `overview.md`, info PDF, schedule CSV, logo originals). It's outside `docs/`, so it isn't published.

## Content guidance (from the course description)

The course is still being planned. Keep the grading breakdown labeled **proposed**, SE Concentration credit as **to be confirmed**, and don't present specific tools as confirmed requirements.
