# Programming 1

- See course info: https://degree-planner.programming.africa/?f=CS101
- See info about Kibo's BSc. Computer Science: https://kibo.school/degree/

## What's here?

```
$ tree .
.
├── README.md
├── book.toml
├── theme/
└── src
    ├── SUMMARY.md
    └── chapter_1.md

```

## course.yml

Anchor configuration for the course and lessons.

Dump the summary.md file to the config file with:

```
python summary-to-yaml.py > course.yml
```

### README.md

You're lookin at it.

### book.toml

Config file for the course. Authors, title, other mdbook settings.

https://rust-lang.github.io/mdBook/format/configuration/index.html

### theme/

Any overrides of the default mdbook theme. Right now, just some custom CSS on
top of the standard mdbook CSS.

https://rust-lang.github.io/mdBook/format/theme/index.html

### src

Holds all the course files.

The static site output will be built to `output`, but that's git ignored.

### src/SUMMARY.md

This gets turned into the sidebar on the site.

It's the text that should show, plus links to other md files in `src/`.

https://rust-lang.github.io/mdBook/format/summary.html

### src/*

These are the pages that actually make up the course. It's nice to put things in folders to organize the different pages. Each week can get a 'cover page' and a page per lesson, in a folder with that name, like

```
working-with-data.md
working-with-data/
    programs-and-comments.md
    variables-and-assignment.md
    data-types-operators-and-expressions.md
    input-and-output.md
```

etc.

### output

To generate the static site, run:

```
mdbook build
```

Output lives here, in `output`.
You can usually ignore these files; git will.

## Getting Started

Install mdbook: https://rust-lang.github.io/mdBook/guide/installation.html

if you use rust:

```
cargo install mdbook
```

Or use your package manager: `brew install mdbook`, or download a release from Github.

### Run the book locally

```
mdbook serve --open
```

## Deployment

We use `vercel` to handle deploys. It takes some setup to connect a repo to
vercel, assign a production domain, and set up auto-deploys.

* Github actions will run `mdbook build` on pushed changes
* All pushes will automatically deploy to vercel
* Vercel will notify the #tech-status channel on Slack with the deploy preview
* If you pushed to `main`, it will also deploy to the live site. Watch out!

## Previews and Drafts

If you'd like to preview changes, push to a branch (like the `draft` branch that will hang around). Check the #tech-status channel in Slack for a link to the preview when you make a change.

Remember - commits to main get built and deployed to the production site; others just get previews.
