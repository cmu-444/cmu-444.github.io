# 17-444 Course Website

Website for CMU 17-444, *Production Machine Learning Systems for Software Engineers* (Carnegie Mellon University in Qatar). Built with [MkDocs](https://www.mkdocs.org/) and [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

## Quick Start

```sh
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
mkdocs serve      # http://localhost:8000/
```

`mkdocs build` writes the static site to `site/`.

## Editing content

- Pages live in `docs/`. A new page also needs an entry under `nav` in `mkdocs.yml`.
- The homepage's Weekly Schedule and This Week sections come from `docs/_data/schedule.yaml` (one entry per weekday, Sun–Thu). After editing it, run `cd docs/_data && python3 update_this_week.py`. CI also does this daily.
- Team surveys go in `docs/_data/teamsurveys.yaml`.
- Staff cards on the homepage come from `docs/_data/staff.yaml`, with photos in `docs/assets/images/`.
- `resources/` holds source material (course description, schedule CSV, logo originals). It sits outside `docs/`, so it is not published.
