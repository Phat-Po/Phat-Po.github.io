# phat-po.github.io — Personal Homepage

> **动手前先查错题本**：接到任何改版、改排版、换图、上线类任务，先用需求里的关键词 grep `docs/known-issues.md docs/known-issues/`（先看目录，不要整本读），命中就按条目避坑并引用 KI 编号。

Pohan Lee's personal homepage, served by GitHub Pages from `main` at https://phat-po.github.io/.

## Stack

- One static file: `index.html` (inline CSS + a little vanilla JS). No build step, no dependencies.
- Images in `assets/`.
- Pushing to `main` publishes the site (~1–2 min). This repo is **public**: anything committed is visible, including this file.

## Design (current: v2, 2026-10)

- Palette: `--bg #fafaf8` / `--ink #0a0a0a` / `--lemon #FFD500`; Helvetica + Menlo. Keep it.
- Sections, top to bottom: poster-size name + SVG illustrated avatar → stats row → thermal-receipt bio (prints line by line) + links → 6-column bento project grid → "On the workbench" marquee → footer.
- Bento sizes: `.s2/.s3/.s4/.s6` = columns spanned out of 6. Real media gets the big cells.
- Text-only covers (`.tc ink|lemon|paper`) type out their `.tc-mono` line on reveal/hover.
- Projects without a demo live as `.ticket`s in the workbench marquee. When one gets a screenshot/GIF/video, move it into the grid as an `<a class="card">`.
- All animation must respect `prefers-reduced-motion`.

## Content rules

- Never mention 台湾 or Shopee in public titles (use "Ecommerce …").
- Event name: "This Should Work · 线下 Vibe Coder 交流会". Thermal printer project is "Idea Ticket Printer".
- GIFs: ffmpeg, fps=8, 560px wide, 64 colors, keep < 3 MB; add `?v=N` to bust cache when replacing.
- 小红书 links use xhslink.com short links; if one stops redirecting, swap in the full note URL.

## Upgrade workflow

1. Draft the new version in `tasks/mockups/` (asset paths `../../assets/`).
2. Show the operator a temporary hosted preview, not localhost.
3. Check phone width: at 390px and 375px, `document.documentElement.scrollWidth` must equal the viewport width (KI-layout-001).
4. After the operator picks, copy into `index.html` (paths → `assets/`), commit only the site files, confirm before push.

## Constraints

- Follow global governance: `~/.claude/CLAUDE.md`.
- `tasks/` and `docs/` are local-only (git-ignored) — internal notes never go to the public repo.
