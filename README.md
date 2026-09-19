# web-foundations-docs

Web制作の共通基礎をまとめる content-only repository です。

このリポジトリは Next.js アプリではありません。共有サイトランタイムは `metyatech/course-docs-site` にあります。

## Overview

このリポジトリには、JavaScript やプログラミング演習の序盤で共通して必要になる Web 制作の前提知識を置きます。

- Webページのしくみ
- ファイル・フォルダ・拡張子
- HTML文書の基本形
- タグ・要素・属性
- 入れ子とインデント
- パス・URL・外部ファイル
- ブラウザで確認する
- コメント

## Verify

Run the canonical verification command from this repository:

```sh
node scripts/verify.mjs
```

What it does:

- runs `markdownlint` for this repository
- locates a local `course-docs-site` checkout automatically when the repos live in the same workspace
- runs `course-docs-site` lint and `build:verified` with `COURSE_CONTENT_SOURCE` set to this repository

## Local preview

Point `course-docs-site` at this repository through `.env.course.local`:

```sh
# In course-docs-site/.env.course.local
COURSE_CONTENT_SOURCE=../web-foundations-docs
```

Then run the site from `course-docs-site`.

## Deploy (Vercel)

Deployment is done via GitHub Actions using the Vercel CLI.
See `.github/workflows/deploy-vercel.yml`.
The workflow checks out `metyatech/course-docs-site`, points `COURSE_CONTENT_SOURCE` at this repository, and deploys the resulting build.

Required GitHub Actions secrets:

- `VERCEL_TOKEN` (a Vercel access token with access to the target project/team)
- `VERCEL_ORG_ID`
- `VERCEL_PROJECT_ID`

## Compliance

- [LICENSE](LICENSE)
- [CONTRIBUTING.md](CONTRIBUTING.md)
- [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)
- [CHANGELOG.md](CHANGELOG.md)

## Repository structure

```text
content/
  _meta.ts
  docs/
    _meta.ts
    web-page-basics/
      index.mdx
    files-folders-extensions/
      index.mdx
    html-document-structure/
      index.mdx
    tags-elements-attributes/
      index.mdx
    nesting-indentation/
      index.mdx
    paths-urls-external-files/
      index.mdx
    browser-preview/
      index.mdx
    comments/
      index.mdx
public/
  img/
    favicon.ico
site.config.ts
```

## Content contract

- `content/` — MDX page content
- `content/**/_meta.ts` — Nextra sidebar ordering
- `public/img/` — static files
- `site.config.ts` — site metadata consumed by `course-docs-site`

Do not add Next.js app runtime files (`next.config.js`, `src/app/`, `package.json`) to this repository.
