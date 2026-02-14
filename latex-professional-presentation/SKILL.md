---
name: latex-professional-presentation
description: Instructions on building a latex beamer presentation for a professional astronomer or software engineer audience. Use this skill when asked to create a latex beamer presentation for a professional audience.
---

# Skill Instructions

Follow the instructions below. See example.md for latex code for
handling figures

---

# SKILL: LaTeX Beamer Presentation Authoring for Professional
  Astronomers and Software Engineers

## Purpose

This skill produces **clear, accurate, and visually clean LaTeX Beamer
presentations** intended for **specialists** in software
engineering/astronomy.

The goal is **technical understanding without loss of correctness**,
while providing a broader perspective.

---

## Scope

This skill applies **exclusively** to presentations created using
**LaTeX Beamer**.

Supported use cases include:

* Astronomy workshop/conference/school talks
* Interdisciplinary seminars
* Talks to software specialists working on astrnomy software

Broad outreach talks are **out of scope** for this skill.

---

## Core Output Requirements

### 1. Document Class and Compilation

* The document **must use**:

  ```latex
  \documentclass{beamer}
  ```
* Output **must compile cleanly with `pdflatex`**
* Unless otherwise specified, the aspect ratio of the presentation must be
16:9
* Use only standard, widely available LaTeX packages
* Ensure:

  * No LaTeX compilation errors
  * Correct math mode usage
  * No broken references or malformed frames

If a `pdflatex` error is reported, the skill **must automatically fix
it** and return corrected LaTeX.

---

### 2. Beamer Theme and Visual Design

* Use a **clean, readable Beamer theme** with no navigational icons
* Slide number should appear at bottom right but don't put the total slide number
* Use beautiful color schemes and fonts always
* Unless otherwise specified, text should be in light colors on a uniform black background
* Colors should be attractive but not gaudy
* Slides must be legible from the back of a large room
* Avoid visual clutter
* Include /home/yogesh/work/images/ncralogo.jpg which is a 697x797 pixel image at bottom right of the title page only
* Animations and overlays may be used **sparingly** if they improve conceptual clarity, but are not required

---

### 3. Frame Structure

Each frame must:

* Have a clear, descriptive title
* Focus on **one idea or concept**
* Use short bullet points or simple diagrams
* Avoid long paragraphs or dense equations

Slides should be self-contained and understandable.

---

### 4. Writing Style and Tone

* Clear, neutral, and explanatory
* Technically accurate but **jargon-minimized**
* No conversational filler or rhetorical questions

---

### 5. Scientific Accuracy and Pedagogy

* All statements must be scientifically correct
* Use analogies **only when they aid understanding**, and explicitly state their limitations
* Clearly separate:

  * Established facts
  * Models or interpretations
  * Open questions

Approximations and simplifications must be acknowledged.

---

### 6. Mathematics and Quantitative Content

* Use mathematics **sparingly**
* Equations should:

  * Illustrate relationships, not derivations
  * Be accompanied by plain-language explanations
* Prefer proportionalities or scaling relations over full formulae
* All symbols must be defined immediately

---

### 7. Figures and Visual Explanations

* Beautiful informative images will be central to the talk. All images sit in a common images folder. Images should be on separate slides, where there will be no text except the title. See example.md for how images are to be formatted. Suggest suitable images by adding latex comments to image slides. Add a credit line at the bottom of all images.
* Additional figures, if needed,  should be produced using **`tikz` and/or `pgfplots`**
* Cartoon diagrams are preferred over plots unless quantitative insight is essential
* Figures must:

  * Be clearly labeled
  * Avoid unnecessary technical detail
  * Include short, explanatory captions


---

### 8. Links and Further Reading

* All links must be **clickable in the PDF**
* Use:

  ```latex
  \usepackage{hyperref}
  ```
* Links may point to:

  * Reputable educational resources
  * Observatory or mission websites
  * Public data portals
* Place links on dedicated “Further Reading” or summary slides

---

### 9. Error Handling and Self-Correction

If the user reports:

* LaTeX compilation errors
* Visual layout problems affecting readability
* Conceptual confusion or misleading explanations

The skill must:

1. Identify the issue
2. Correct the LaTeX and/or explanation
3. Return a **fully corrected, compilable Beamer document**

---

## Explicit Non-Goals

This skill must **not**:

* Include dense derivations or unexplained equations
* Use outreach cliches, hype, or sensational language
* Invent data or oversimplify to the point of incorrectness
* Use non-LaTeX formats

---

## Expected User Inputs

Typical inputs may include:

* Target audience background (e.g. astronomers, software engineers, policy makers)
* Talk duration or approximate slide count
* Topic and desired depth
* Requests for conceptual diagrams
* `pdflatex` error messages, if any

Ask user for clarifications, if in doubt.

---

## Output Guarantee

Every response produced by this skill must be:

* Scientifically correct
* Clearly written and well-structured
* Valid LaTeX Beamer
* Fully `pdflatex`-compilable with zero errors other than the occasional overflow
---
