---
name: latex-conference-proceeding
description: Autogenerate a LaTeX conference proceedings article from user-supplied content instructions, optionally using a user-supplied conference template (class file, style file, or formatting instructions). Use this skill when asked to write, draft, or revise a conference proceedings paper, workshop proceedings contribution, or similar short formal scientific article, as opposed to a beamer talk or a full journal manuscript.
---

# Skill Instructions

Follow the instructions below when drafting or revising a LaTeX conference
proceedings article. See `example.md` for figure/table macros and a generic
fallback article skeleton to use when the user has not supplied a template.

---

# SKILL: LaTeX Conference Proceedings Article Authoring

## Purpose

This skill produces **formal, accurate, and correctly formatted LaTeX
conference proceedings articles**. The user supplies the scientific or
technical content — results, data, figures, tables, references — in detail,
and may supply a conference-specific LaTeX template (class/style files, a
skeleton `.tex` file, or written formatting instructions). The skill's job is
to turn that content into a complete, compiling article that respects every
constraint the template or the user imposes.

---

## Scope

This skill applies to short-to-medium formal write-ups intended for
publication in conference, workshop, or symposium proceedings (e.g. IAU
Symposia, ASP Conference Series, EPJ Web of Conferences, SPIE, IEEE
conference proceedings, Copernicus proceedings volumes, LNCS-style computer
science proceedings). It is not intended for:

* Beamer talks or posters (see the presentation/lecture skills for slides)
* Full journal articles with no page or format constraints
* Public-outreach writing

---

## Core Output Requirements

### 1. Template Handling

* If the user supplies a template — a document class, `.sty` file, example
  `.tex` skeleton, or an author-guidelines document — **use it as the
  authoritative source of structure and formatting**. Do not substitute a
  different class or override its layout choices.
* Search the supplied material for embedded formatting rules: LaTeX comments
  in the template, a separate instructions/guidelines file, or prose the user
  pastes in. Extract and obey constraints such as:
  * Maximum page count or word count
  * Required document class options (font size, columns, paper size)
  * Required or forbidden sections
  * Figure/table format, resolution, and placement rules
  * Abstract length limits and keyword requirements
  * Citation and bibliography style (`.bst` file, natbib style, or a fixed
    reference format)
* If no template is supplied, ask the user which proceedings series applies,
  if known. If that is also unknown or the user wants a generic draft, fall
  back to the skeleton in `example.md` (`\documentclass{article}`, two
  columns, 11pt) and clearly mark it in a comment as a generic placeholder
  the user must swap for the venue's actual class file before submission.
* Never invent a plausible-looking class name or `\documentclass` option to
  imitate a specific conference series unless the user has confirmed the
  correct package name; ask rather than guess.

### 2. Compilation

* The document must compile cleanly with `pdflatex` (or the compiler the
  template explicitly requires, e.g. `pdflatex` + `bibtex`).
* Use only the packages included with the template, plus standard, widely
  available packages when the template is silent.
* Correct math mode, labels, cross-references (`\ref`, `\cite`), and
  environment syntax.
* If a `pdflatex`/`bibtex` error is reported, identify the underlying cause
  and return a complete corrected document rather than a patch description.

### 3. Content Fidelity

* The user is the domain authority for the science or technical content.
  Do not invent data, results, numerical values, affiliations, funding
  sources, or citations.
* Where the user's instructions leave a section underspecified, insert a
  clearly marked placeholder (e.g. `% TODO(author): summarize dataset X
  here`) rather than fabricating plausible-sounding content.
* Preserve user-supplied numbers, equations, and claims verbatim; edit only
  for grammar, formality, and clarity, not scientific substance.
* Flag apparent inconsistencies (e.g. a number in the text that disagrees
  with a table) instead of silently resolving them.

### 4. Document Structure

Unless the template dictates otherwise, structure the article as:

1. Title, author list, affiliations, and corresponding-author marking
2. Abstract (respecting any word/line limit) and keywords if required
3. Introduction — context, motivation, and goals
4. Data/Observations or Methods, as appropriate to the field
5. Results
6. Discussion
7. Conclusions/Summary
8. Acknowledgments
9. References

Follow the template's required section names, numbering style, and order
exactly when it specifies them; the list above is only a fallback default.

### 5. Formal Language and Register

* Write in a formal, precise, scientific register appropriate for a peer-read
  proceedings volume.
* Use third-person, impersonal constructions by default (or first-person
  plural, "we", if that is the field/template convention); do not switch
  registers mid-document.
* No contractions, colloquialisms, rhetorical questions, hype, or marketing
  language ("groundbreaking", "revolutionary", "cutting-edge") unless
  directly supported and requested.
* Define every acronym and symbol at first use; use notation consistently
  throughout.
* Prefer precise, falsifiable statements over vague claims; distinguish
  observation, model, inference, and interpretation.

### 6. Length and Page Limits

* Treat any stated page, word, or line limit as a hard constraint.
* When content threatens to exceed the limit, tighten prose, move
  supplementary material to a footnote or reference where the template
  allows it, and only as a last resort ask the user which content to cut —
  never silently drop required results or the required sections above.
* Do not alter font size, margins, or column count to force-fit content
  unless the template explicitly allows author discretion there.

### 7. Figures and Tables

* Follow the template's figure/table conventions (placement, caption
  position, numbering, allowed formats). See `example.md` for a generic
  convention (captions below figures, above tables) to use when the template
  is silent.
* Every figure and table must carry a `\label` and be referenced from the
  text via `\ref`.
* Credit externally sourced figures, data, or tables with a citation or
  explicit credit line.
* When an image the user described has not been supplied, add a LaTeX
  comment placeholder describing what is expected, rather than fabricating
  or substituting an unrelated image.
* Keep captions self-contained but concise; do not repeat the full body text
  in the caption.

### 8. Equations

* Use numbered `equation`/`align` environments for any equation referenced
  elsewhere in the text; use unnumbered environments for purely illustrative
  ones only if the template's convention allows it.
* Define every symbol on first use, including units.
* Keep notation consistent with any convention the field or template
  specifies (e.g. IAU-recommended astronomical notation).

### 9. Citations and Bibliography

* Use `\cite` (or the template's citation macro) consistently; do not write
  bare author-year text where the template expects a citation command.
* Use the bibliography style (`.bst` file or natbib style) the template
  specifies. If none is specified, use `natbib` with a plain numeric or
  author-year style and say so explicitly.
* Never fabricate a reference, DOI, arXiv identifier, or page number. If the
  user has not supplied full bibliographic details for a citation, insert it
  as a clearly marked placeholder entry in the `.bib` file instead of
  guessing.

### 10. Error Handling and Revision

If the user reports a compilation error, a formatting violation of the
template's rules, or a factual/content problem:

1. Identify the underlying cause.
2. Correct the LaTeX or content directly rather than applying a cosmetic
   workaround (e.g. do not hide an overfull box by shrinking unrelated text).
3. Preserve template compliance and content fidelity.
4. Return the complete corrected document(s), not just a diff description.

---

## Explicit Non-Goals

This skill must not:

* Substitute a different document class or style file than the one the user
  supplied, or fabricate one that merely resembles a real conference's class.
* Invent data, results, citations, affiliations, or funding acknowledgments.
* Silently exceed or ignore a stated page/word limit.
* Produce beamer slides, posters, or outreach copy under this skill.
* Loosen formal register into conversational or promotional language.

---

## Expected User Inputs

Useful inputs include:

* A template: class/style files, an example `.tex`, and/or an author
  guidelines document, or the name of the proceedings series if no template
  file is available
* Any separate formatting instructions (page limit, figure/table rules,
  citation style) not embedded in the template itself
* Title, author list, and affiliations
* Detailed content: the scientific/technical material for each section,
  data, results, figures, tables, and references to include
* Existing LaTeX source or `pdflatex`/`bibtex` error messages, for revisions

If a required constraint (page limit, mandatory sections, citation style) is
genuinely unknown and not recoverable from a supplied template, ask a
focused clarifying question before drafting rather than guessing.

---

## Output Guarantee

Every article produced with this skill must be:

* Faithful to the user-supplied content, with no fabricated data or
  citations
* Compliant with the supplied template's structure and constraints, or
  clearly marked as using a generic fallback when none was supplied
* Written in a formal, precise, scientific register
* Valid LaTeX that compiles with `pdflatex` (and `bibtex`, if applicable)
  without errors, apart from non-fatal overfull-box warnings that should
  still be minimized
