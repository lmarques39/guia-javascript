---
name: manage-readme-chapters
description: Add or rename a chapter/section in README.md (or a GitHub Wiki page) in this guia-javascript repo while keeping the manual Índice and the Wiki's _Sidebar links working. Use whenever a heading in README.md or a wiki page changes.
---

This repo's `README.md` has a hand-written **Índice** near the top that links to its own headings by anchor, and the project's GitHub Wiki (https://github.com/lmarques39/guia-javascript/wiki) has a `_Sidebar` that links into README/wiki headings the same way. Both break silently if a heading changes without updating the link.

## GitHub anchor-generation rule
GitHub auto-generates a heading's anchor as:
1. Lowercase the text.
2. Replace spaces with hyphens.
3. Strip punctuation (`.`, `?`, `:`, etc.) — accented letters (á, é, ã, ç...) are kept as-is.

Example: `## 2.1. O que é JavaScript?` → `#21-o-que-é-javascript`.
Example: `# 1. Guia Básico de JavaScript` → `#1-guia-básico-de-javascript`.

## Procedure when adding a new chapter
1. Add the heading using the existing pattern: `# N. Título` for top-level chapters, `## N.M. Subtítulo` for subsections (numbering matches the existing chapters 1–9 in README.md).
2. Compute its anchor with the rule above and add a matching line to the **Índice** block at the top of `README.md`, nested under its parent the same way existing entries are (see the current Índice for the indentation pattern).
3. If the same section is mirrored in the Wiki's `_Sidebar`, add/update the corresponding link there too, using the same anchor rule.
4. Per [[feedback-review-before-commit]] (session memory) — show the diff/new text to the user first; do not `git add`/`commit`/`push` unless they explicitly ask.

## Procedure when renaming an existing heading
1. Recompute the anchor for the new heading text.
2. Update every link that pointed at the old anchor: the README's own Índice, and the Wiki `_Sidebar` if it links there too.
3. Grep for the old anchor string (`#old-anchor-text`) across `README.md` and, if you have the wiki content available, the wiki pages, to make sure nothing was missed.

## Note on the Wiki
The Wiki is a separate Git repo/deliverable from `README.md` (goal, structure, chosen language, author, plus a fork→clone→branch→commit→merge-request collaboration guide for classmates). Its `_Sidebar` currently lists: **Home** ("Sobre o Projeto"), **Como criar o projeto**, **Como colaborar**. Treat its content edits with the same "draft first, no auto-push" rule as the README.
