# Repository Guidelines

## Project Structure & Module Organization

This repository contains a collection of small static HTML tools. The root
`index.html` lists available tools and links to each tool directory. Each tool
lives in its own folder with an `index.html`, for example `duration-sum/`,
`csv-to-insert-sql/`, or `csv-duration-total/`.

Use `template.html` as the starting point for new tools so layout, navigation,
and Tailwind styling stay consistent. Static data used by a tool should remain
inside that tool directory, as in `location-finder/data.csv`.

## Build, Test, and Development Commands

There is no build step or package manager setup. Tools are plain HTML pages using
Tailwind from the CDN.

Useful local commands:

```bash
python3 -m http.server 8000
```

Serves the repository locally at `http://localhost:8000`.

```bash
rg "search text"
```

Searches quickly across tools.

```bash
git diff
```

Reviews pending changes before committing.

## Coding Style & Naming Conventions

Keep each tool self-contained in its own `index.html`. Use 4-space indentation
for HTML, CSS classes, and inline JavaScript, matching the existing files. Prefer
descriptive IDs and function names such as `calculateTotal`, `copyTotal`, and
`parseCsv`.

Use kebab-case for tool directories, for example `markdown-minimizer` or
`fraction-reducer`. Keep UI text in French when adding user-facing copy to match
the existing tools.

## Testing Guidelines

There is no automated test framework. Validate changes manually in a browser
through the local HTTP server. For calculators and parsers, test representative
inputs, empty inputs, invalid inputs, and copy-to-clipboard behavior.

When adding a tool, verify that:

- the page works directly at `/<tool-name>/`;
- the home icon returns to `/`;
- the root `index.html` includes the new tool;
- mobile-width layout remains usable.

## Commit & Pull Request Guidelines

Recent commits use short conventional prefixes such as `feat:`, `fix:`, and
`style:`. Follow that pattern:

```bash
git commit -m "feat: add csv duration total tool"
```

Pull requests should include a concise description, screenshots or screen
recordings for UI changes, manual test notes, and any linked issue or context.
Keep changes scoped to the requested tool unless shared behavior must change.

## Agent-Specific Instructions

Before adding a new tool, check existing directories for similar behavior and
reuse the template style. Do not introduce a build system, dependency manager, or
framework unless the repository owner explicitly requests it.
