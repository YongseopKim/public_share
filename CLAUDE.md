# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

The **public face** of a private writing practice. Everything here has been deliberately
published — this repository is world-readable on GitHub, and must be treated that way at
every moment.

**Its first job is to explain the user's career.** `README.md` is the primary artifact and
the landing page; anything else here exists because it supports that. When a choice comes
up — what to publish, how to order it, what to cut — resolve it in favour of a reader
trying to understand what this person has built and can do.

This is not a code project — there are no build/test/lint commands. It is always operated
through an agent (Claude Code or Codex); `AGENTS.md` is a symlink to this file, so rules
written here apply to every agent.

Since this is not a code repository, the global worktree rule does not apply — work
directly on main.

## Absolute rule: nothing is authored here

**This repository is never a destination for new writing.** It has no drafts, no inbox, no
half-formed notes. Every file is the public edition of something that already exists,
finished, in the private source repository.

If the user starts writing something new in a session scoped to this repository, that is a
signal the session is in the wrong repository — say so and ask where the original should
live. Do not create the file here and plan to backfill an original later.

**There are no exceptions, `README.md` included** (settled 2026-07-19). The profile is
written and revised as a document in `cb`; what lands here is its public edition. It is
tempting to treat the profile as public-only — it has no private half, so why route it
through a private repository — but the career narrative is exactly the material that gets
reworked over time, and it needs a place to be drafted where a bad sentence is not
already published. A rule with one exception also decays into a rule with several.

## Where content comes from

The source of truth is **`cb`** (git remote: `github.com/YongseopKim/cb`), a private
commonplace book — quotes, ideas, technical notes, essays. `cb` in turn draws on `journal`,
a private life record where the career record itself lives, but that stage is upstream of
`cb` and invisible from here. There is no path from `journal` to this repository that does
not pass through `cb`, and that is deliberate: the raw career record is not publishable as
written, and `cb` is where it becomes prose.

```
journal  (private)  what happened, on the time axis
   ↓                the raw material
cb       (private)  the thought, worked into finished writing
   ↓                the canonical original
public_share        the public edition
```

- A file here is a **rewrite**, not a copy. The `cb` original is canonical; the public
  edition is re-cut for a public reader — private detail removed, names and employers
  handled deliberately, length adjusted, translated where that serves the audience. The
  two files are different documents, which is why this does not violate the
  no-duplication rule that governs the private repositories.
- Because it is a rewrite, **the original may not be reconstructed from what is here**,
  and edits made here do not flow back. A correction to the substance belongs in the `cb`
  original first, and then in the public edition. A correction to the wording of the
  public edition alone is fine and stops here.

## Never leak the private side

The private repositories are private. This one is public. That asymmetry produces rules
that deliberately break the symmetry used between the private repositories:

- **No back-references.** Never write a `cb:` or `journal:` reference, a private repository
  name, or a path into one, in any file here — not in front matter, not in a comment, not
  in a commit message. The link between an original and its public edition is recorded on
  the `cb` side only.
- **No provenance chains.** `cb` entries carry `source:` front matter pointing at raw and
  derived files. Strip it when publishing.
- **Assume permanence.** A commit that exposes something is public the moment it is
  pushed, and remains recoverable after any later deletion. Check before the commit, not
  after.
- When unsure whether a specific detail is publishable, **ask the user** — do not decide
  it silently in either direction.

## Language

Chosen per document, not by a repository-wide rule:

- The profile (`README.md`) and anything career-facing: **English**.
- Technical and study notes: **Korean**, matching how they were written in `cb`.
- Commit messages: **English**.
- Conversation with the user: **Korean**.

When publishing a note whose audience is ambiguous, ask.

## Structure

Flat root, deliberately. Filenames are not uniform (`250326_survey_x.md` alongside
`claude_code_plugins.md`) and existing files are left as they are — renaming a published
file breaks whatever links to it.

For new files, prefer `YYMMDD_short_slug.md` where the note is tied to a date, and a plain
descriptive slug where it is not.

If the root ever outgrows a flat list, propose a reorganization — never perform one
unilaterally, and weigh it against the broken-link cost.

## Publishing procedure

Given a `cb` original the user has chosen to publish:

1. Read the original in full.
2. Write the public edition here as a new file — rewritten, provenance stripped, private
   detail removed.
3. Show the user the diff between what the original said and what the public edition says
   before committing. This is the disclosure review; it is not optional.
4. Commit and push.
5. Record the link on the `cb` side (`public:` front matter on the original). That write
   happens in a `cb` session, not this one.

## Related repository: cb

From a session scoped to this repository, `cb` is **read-only** — read the original to
publish it, never edit it. Writes to `cb`, including the `public:` back-link in step 5,
happen in `cb` sessions.

Resolving the location of `cb` at use time: try the sibling directory `../cb` first, and
verify it is the right repository by its git remote. If it is not there, ask the user
where it is rather than searching the filesystem broadly.

This section is mirrored by the matching section in `cb`'s rule file. The duplication is
deliberate — each repository is cloned and operated on its own, so neither may depend on
the other's file or on a shared parent being present. Deliberate duplication still has to
be maintained: when editing this section, read the counterpart in the same session and
reconcile both, or state plainly that only one side changed and why.

There is no relationship section for `journal`, and there should not be one: nothing
travels between `journal` and this repository directly.

## Commits

Short, English. Prefixes: `publish:` (new public edition), `edit:` (wording change to an
existing public file), `remove:` (unpublishing a file), `docs:` (README/CLAUDE.md).

The no-leak rule covers commit messages too. A message like "move X to cb" names a private
repository and is itself a leak — say what changed here, not where it went.
