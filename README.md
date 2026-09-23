# gt-gt-1000

GT 1000 &mdash; First-Year Seminar, Physics

This repository contains course materials for GT 1000 (First-Year Seminar), section D03 for Physics, Astrophysics, and Applied Physics majors at the Georgia Institute of Technology. Materials include the syllabus, welcome page, assignment pages, supplemental guides, and lecture files intended for students and instructors.

The site is built with [Quarto](https://quarto.org/). Project configuration is in `_quarto.yml`; visual styling is in `gatech-theme.css`. The live course site is hosted at **[ajsteinmetz.github.io/gt-gt-1000](https://ajsteinmetz.github.io/gt-gt-1000/)** via GitHub Pages.

This site was forked from [gt-phys-4604](https://github.com/ajsteinmetz/gt-phys-4604), which uses the same Quarto scaffold and Georgia Tech theme.

## Status

The scaffold is complete and renders, but course content is still being written. Unfinished items are marked with `TBD` in the rendered text and `<!-- TODO: ... -->` in the source. To list everything outstanding:

```bash
grep -rn "TODO\|TBD" --include="*.qmd" .
```

Outstanding at minimum: the weekly schedule, the three project assignment pages, and Canvas course and assignment links.

## Contents

- `index.qmd` &mdash; welcome page and course overview
- `course-files/` &mdash; core course pages:
  - `syllabus.qmd` &mdash; full syllabus and course policies
  - `syllabus-latex/gt-1000-syllabus-fall26.tex` &mdash; LaTeX source for the printable syllabus PDF; the source of truth for course facts
- `assignments/` &mdash; Quarto source for the three graded projects:
  - `team-project.qmd` &mdash; Team Project (25%)
  - `academic-planning.qmd` &mdash; Academic Planning Project (25%)
  - `career-readiness.qmd` &mdash; Career Readiness Project (25%)
- `supplemental/` &mdash; additional reference guides:
  - `resume-cv.qmd` &mdash; Resume vs. Academic CV
  - `technical-writing.qmd` &mdash; Technical and Professional Writing
  - `peer-feedback.qmd` &mdash; Giving and Receiving Peer Feedback
- `lectures/` &mdash; lecture slides (Quarto RevealJS) and lecture index
- `references.bib` &mdash; project-wide bibliography, cited from the supplemental pages and lecture slides
- `gatech-theme.css` &mdash; site theme; `lectures/gatech-revealjs.css` &mdash; slide theme

## Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) 1.4 or later

`lectures/lecture-01.qmd` contains executable Python cells that use **matplotlib** and **numpy**. Their rendered output is committed under `_freeze/`, so a normal render does **not** require a Python environment. If you edit that file or delete `_freeze/`, Quarto will re-execute the cells and Python with those packages becomes required.

## Local Development

To render the full site locally:

```bash
quarto render
```

Rendered output is written to `_site/`. To preview the site in a browser with live reload:

```bash
quarto preview
```

To render a single file:

```bash
quarto render assignments/team-project.qmd
```

Quarto uses `freeze: auto` (configured in `_quarto.yml`), so unchanged files are not re-rendered on subsequent runs. To force a full re-render, delete the `_freeze/` directory before running `quarto render` &mdash; but see the note about Python above.

## Publishing

The site is deployed to GitHub Pages from the `gh-pages` branch. To publish:

```bash
quarto publish gh-pages
```

Quarto will render the project, update the `gh-pages` branch, and push to the remote. GitHub Pages then serves the updated site at [ajsteinmetz.github.io/gt-gt-1000](https://ajsteinmetz.github.io/gt-gt-1000/) within a few minutes.

The `gh-pages` branch contains only rendered output and should not be edited directly.

## Semester Rollover

At the end of each semester, tag the repository to preserve a snapshot before updating for the next term:

```bash
git tag fall-2026
git push origin fall-2026
```

Then update the semester, section, CRN, meeting time, and schedule dates in `index.qmd`, `course-files/syllabus.qmd`, and `course-files/syllabus-latex/gt-1000-syllabus-fall26.tex`, add any new lectures to `lectures/index.qmd`, and republish.

## License

Course materials are licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). See `LICENSE`.
