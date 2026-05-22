# Contributing

Thank you for your interest in contributing to `web-foundations-docs`.

## Development setup

```sh
git clone https://github.com/metyatech/web-foundations-docs.git
cd web-foundations-docs
```

## Local preview

1. Clone `metyatech/course-docs-site`.
2. Run `npm install` in that repo.
3. Create `course-docs-site/.env.course.local` with `COURSE_CONTENT_SOURCE` set to this repository.
4. Start the dev server with `npm run dev`.

Use any local path that is valid from the `course-docs-site` checkout. If the two repositories are siblings, `../web-foundations-docs` works.

## Verification

Run the full verification suite before each commit:

- `node scripts/verify.mjs`

If `course-docs-site` is not in the same workspace, set `COURSE_DOCS_SITE_DIR` to that checkout before running the verify script.

## Submitting changes

1. Fork the repository and create a feature branch.
2. Open a pull request with a clear description of the change.

## Scope

This repository is **content-only** and contains shared Web foundation documentation consumed by course sites. Keep PRs scoped to content, metadata, and content-repository automation. Runtime/site changes belong in `course-docs-site` or `course-docs-platform`.
