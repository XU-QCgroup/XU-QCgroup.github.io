# XU-QCgroup.github.io

Research website for the XU-QCgroup at Ames National Laboratory and Iowa State University:
https://xu-qcgroup.github.io

GitHub Pages builds the site with Jekyll each time `main` changes; nothing needs to be installed to publish.
Header, navigation and footer live once in `_layouts/default.html`. Most updates are edits to the small
text files in `_data/`.

## Common updates

**Add a news item**: add to the top of `_data/news.yml` (order doesn't matter; it sorts by `date`).
The home page shows the newest three automatically.

```yaml
- date: 2026-11
  label: November 2026
  text: Sam Leonard presented at the ACS Fall Meeting.
  image: images/news/sam-acs-2026.jpg      # optional
  image_alt: Sam presenting his poster      # optional
```

**Add or update a person**: edit `_data/people.yml`. Put the photo in `images/people/` (about 400 px tall).
Empty fields are hidden, and a section with no members is hidden.

```yaml
    - name: New Student
      photo: images/people/new-student.jpg
      role: Graduate Student, Department of Chemistry, Iowa State University
      interests: ...
      project: ...
      email: newstudent@iastate.edu
```

**Add a paper**: add an entry to `papers` in `_data/publications.yml`. Papers from `recent_since` on
appear under "Recent"; older ones are grouped by `topic`. "P. Xu" is bolded and names listed in
`group_authors` (`_config.yml`) are marked as group members automatically. Add `toc: images/toc/file.png`
to show a table-of-contents graphic.

**Replace a figure placeholder**: put the image in `images/research/` and give the include a `src`:

```liquid
{% include figure.html src="images/research/qm-efp.png" alt="QM/EFP schematic" caption="..." %}
```

Placeholders: `index.html` (hero + three research cards) and `research.html` (one per theme).

**Profile links** (Google Scholar, ORCID, GitHub, CV, ...): `_data/links.yml`. An empty `url` hides the link.

## Visit statistics (private)

Visits are counted with [GoatCounter](https://www.goatcounter.com) when `goatcounter` is set in `_config.yml`.
Statistics are only visible on your GoatCounter dashboard, not on the site. Local previews are not counted.

## Preview locally (optional)

Needs Ruby ≥ 2.7 and Jekyll: `gem install jekyll`, then `jekyll serve` and open http://localhost:4000.

## Still to fill in (search for `TODO`)

- `_config.yml`: `funding` acknowledgment (shown in footer and on Research)
- `_data/links.yml`: Ames Lab profile, ISU profile, CV
- `_data/people.yml`: Peng's short bio; Gregory Curtin's photo, title, interests, project, email; review Sam's draft interests/project
- `_data/publications.yml`: Connor's poster title and author list
- `contact.html`: `office` (building and room)
- `opportunities.html`: `status` (current openings)
- Figures: 3 placeholders on `research.html`, 4 on `index.html`
