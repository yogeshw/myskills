---
name: latex-astronomy-lecture-course
description: Create rigorous LaTeX Beamer lectures for graduate astronomy courses aimed at PhD students, postdoctoral researchers, and early-career faculty. Use this skill for astronomy course lectures, lecture series, or pedagogical seminar presentations that require undergraduate-physics-level mathematics as a prerequisite.
---

# Skill Instructions

Follow these instructions when creating or revising a LaTeX Beamer
presentation for an astronomy lecture course. See `example.md` for the
required figure macros and image-path convention.

---

# SKILL: LaTeX Beamer Astronomy Lecture Authoring

## Purpose

This skill produces **rigorous, teachable, and visually clear LaTeX Beamer
lectures** for astronomy courses aimed primarily at:

* Graduate students in astronomy or physics
* Postdoctoral researchers
* Young faculty members

The material should assume the mathematical preparation of a strong
final-year undergraduate physics student at a good university. It may extend
their astronomy background, but it must not assume prior specialist knowledge
without supplying the necessary context, definitions, or references.

The goal is to develop durable physical understanding: connect observations,
models, equations, approximations, and their domains of validity.

---

## Scope

This skill applies exclusively to **LaTeX Beamer** materials, including:

* Stand-alone astronomy lectures
* Coherent lecture series and short courses
* Graduate-school or advanced undergraduate course modules
* Research-oriented pedagogical seminars

It is not intended for broad public outreach, conference flash talks, or
slide decks that only summarize research results.

---

## Core Output Requirements

### 1. Document Class and Compilation

* Use:

  ```latex
  \documentclass[aspectratio=169]{beamer}
  ```

  unless the user requests a different aspect ratio.
* The document must compile cleanly with `pdflatex`.
* Use only standard, widely available LaTeX packages unless a nonstandard
  package is explicitly justified.
* Use correct math mode, labels, references, citations, and frame syntax.
* Fix any reported `pdflatex` error and return a complete corrected document.

### 2. Theme and Visual Design

* Use a clean, readable Beamer theme with navigation symbols disabled.
* Display the current slide number at bottom right; do not show the total
  number of slides.
* Unless otherwise requested, use light text on a uniform black background,
  with a restrained, high-contrast accent palette.
* Make all text, plots, axes, legends, and equations legible from the back of
  a lecture room.
* Put `/home/yogesh/work/images/ncralogo.jpg` at the bottom right of the
  title page only. It is a 697x797 pixel image.
* Use overlays or animations only when they reveal the logic of a derivation
  or a physical process; never use them as decoration.

### 3. Course-Level Structure

For a lecture or lecture series, organize material as a coherent teaching
sequence:

1. State the topic, prerequisites, learning objectives, and physical
   questions at the start.
2. Build the required observational and theoretical context before relying on
   it.
3. Derive or motivate the central results in logically ordered steps.
4. Interpret each result physically and connect it to an observable,
   astrophysical system, or numerical estimate.
5. End with a concise summary, assumptions and limitations, and selected
   further reading.

When creating multiple lectures, maintain consistent notation and explicitly
link each lecture to the preceding and following material.

### 4. Frame Design

Each frame must have a descriptive title and a clear instructional purpose.
Use an appropriate mix of:

* Concept or motivation frames
* Definition and notation frames
* Worked derivation frames
* Physical interpretation frames
* Observation, simulation, or data-analysis frames
* Short calculation or discussion prompt frames
* Summary and transition frames

Prefer one central idea per frame. A multi-slide derivation is encouraged when
needed for readability; do not compress a derivation into an unreadable slide.
Avoid long prose paragraphs and dense collections of unrelated equations.

---

## Mathematics and Quantitative Reasoning

### Expected Level

Use mathematics appropriate for a final-year undergraduate physics student,
including when relevant:

* Multivariable calculus, ordinary differential equations, and dimensional
  analysis
* Vector calculus and introductory tensor notation
* Linear algebra, eigenvalue problems, and Fourier methods
* Classical mechanics, electromagnetism, thermodynamics, and statistical
  mechanics
* Probability, uncertainty propagation, and basic inference
* Order-of-magnitude estimates and scaling arguments

Introduce advanced methods before use. Do not assume familiarity with
general relativity, radiative transfer, kinetic theory, plasma physics,
cosmological perturbation theory, Bayesian computation, or advanced
statistical methods unless the lecture explicitly establishes the required
tools.

### Derivations

* Derive important results when the derivation teaches reusable physics,
  exposes assumptions, or prevents a common misconception.
* State the starting equations, definitions, coordinate system, boundary or
  initial conditions, and approximations.
* Define every symbol on first use, including conventions and units where
  relevant.
* Give a brief physical interpretation after each nontrivial step or at a
  natural pause in a multi-frame derivation.
* Clearly distinguish exact results, controlled approximations, heuristic
  arguments, and empirical fitting formulae.
* Use `\sim`, `\propto`, and order-of-magnitude estimates deliberately; state
  what factors have been neglected.
* Do not omit algebraic steps that are essential for the audience to follow,
  but move routine algebra to a compact sequence or optional appendix frame.

### Quantitative Examples

* Include numerical scales in SI or cgs units as appropriate to the subfield;
  state the chosen unit convention.
* Check dimensions, limiting cases, and physical signs in displayed results.
* Where useful, evaluate a representative astrophysical example rather than
  leaving equations abstract.
* Identify which quantities are directly observed and which are inferred
  through a model.

---

## Scientific Accuracy and Pedagogy

* All scientific statements must be accurate and use current standard
  terminology.
* Separate observations, theoretical models, interpretations, and open
  questions.
* State the regime in which a model applies and where its assumptions fail.
* Distinguish correlation from causation and measurement from model-dependent
  inference.
* Use analogies only when they assist understanding, and immediately state
  their limits.
* Surface common conceptual pitfalls when they are relevant, especially
  confusing observables with intrinsic quantities, reference-frame errors,
  selection effects, and inappropriate equilibrium assumptions.
* Make the lecture self-contained at its stated prerequisite level; cite a
  source rather than silently assuming a specialized result.

---

## Figures, Data, and Visual Explanations

Visuals are central to the lecture and must do explanatory work.

* Place supplied images in the common images directory and use the macros in
  `example.md`. Prefer `\myfigbig` for most image slides.
* For an image-led frame, use no text beyond the title, a concise credit line,
  and essential labels or annotations.
* Add a LaTeX comment on each image slide suggesting a suitable image when an
  image has not yet been supplied.
* Credit every externally sourced image, figure, plot, or dataset at the
  bottom of the frame, with a clickable hyperlink where possible. Download any external image you want to use in the slides and place it in /home/yogesh/work/images with a suitable name
* Preserve meaningful plot axes, units, error bars, and colour-bar labels.
  Simplify only after ensuring the omitted detail is not needed for the
  argument.
* Use `tikz` and/or `pgfplots` for schematic diagrams, derivation aids, and
  plots that must match the lecture notation.
* Prefer a diagram when spatial, causal, or geometric reasoning is central;
  prefer a quantitative plot when the value lies in the trend, comparison, or
  uncertainty.
* Label diagrams and define visual encodings in a legend or nearby text.

---

## Writing Style

* Write clearly, precisely, and professionally.
* Use complete but concise sentences for claims and explanations.
* Prefer active definitions and concrete physical language over vague labels.
* Minimize jargon; define unavoidable specialist terms at first use.
* Do not use conversational filler, hype, outreach cliches, or rhetorical
  questions.
* Use notation consistently throughout the deck and across a lecture series.

---

## References and Links

* Make all links clickable in the PDF. Load:

  ```latex
  \usepackage{hyperref}
  ```

* Cite foundational papers, review articles, textbooks, surveys, missions,
  observatories, simulations, and data releases where they first support a
  substantive claim or figure.
* Include a focused further-reading slide with a small number of high-value
  sources, organized by topic when useful.
* Do not ever fabricate citations, numerical values, data products, or image
  credits. If a source is unknown, mark it clearly for the author to supply.

---

## Error Handling and Revision

If the user reports a compilation error, layout problem, scientific concern,
or pedagogical ambiguity:

1. Identify the underlying issue.
2. Correct the LaTeX, science, or explanation rather than applying a cosmetic
   workaround.
3. Preserve the intended level of mathematical rigor.
4. Return a complete, compilable Beamer document or the requested corrected
   portion.

---

## Explicit Non-Goals

This skill must not:

* Dilute a course lecture into a research-talk summary or public-outreach talk.
* Avoid essential mathematics merely to make slides look simpler.
* Present unexplained equations, hidden assumptions, or unsupported claims.
* Use equations so densely that the lecture cannot be followed live.
* Invent data, references, images, citations, or observational conclusions.
* Use formats other than LaTeX Beamer.

---

## Expected User Inputs

Useful inputs include:

* Topic, subfield, and desired learning outcomes
* Lecture duration, number of lectures, and target slide count
* Audience prerequisites and expected mathematical background
* Required concepts, datasets, papers, instruments, or case studies
* Preferred balance between derivation, observation, and discussion
* Existing LaTeX source, figures, or `pdflatex` errors

If a crucial pedagogical choice remains ambiguous, ask a focused clarification
question before drafting the lecture.

---

## Output Guarantee

Every presentation created with this skill must be:

* Scientifically accurate at the stated level
* Pedagogically sequenced and mathematically transparent
* Clear enough for live teaching and later self-study
* Valid LaTeX Beamer that compiles with `pdflatex` without errors, apart from
  non-fatal overfull-box warnings that should still be minimized
