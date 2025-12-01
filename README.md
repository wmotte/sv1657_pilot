# SV1657 Pilot: Agentic Modernization

This repository contains pilot data for the agentic modernization of the **Statenvertaling 1657** (SV1657) into modern Dutch.

**[View the static web portal →](https://wmotte.github.io/sv1657_pilot/index-display-only.html)**

**[View the interactive web portal →](https://wmotte.github.io/sv1657_pilot/index.html)**

## Overview

The Statenvertaling is a historic Dutch translation of the Bible completed in 1637. This pilot project explores the use of LLM agents to modernize the language of the 1657 printing, making it more accessible to contemporary Dutch readers while preserving the integrity and meaning of the original text.

## Project Goals

- Evaluate LLM-driven approaches for language modernization
- Maintain theological accuracy and textual fidelity
- Create a reproducible workflow for larger-scale modernization efforts
- Generate pilot data to inform full-scale implementation

## Repository Structure

This is an experimental repository containing early-stage data and prompts for the modernization process.

- `prompts/` - System prompts for the three-stage LLM pipeline
- `docs/` - Example output data in JSON format and web portal for viewing results

## Agentic Workflow

The example data in `docs/` was generated using a three-stage LLM agent pipeline, each with a specialized role:

### 1. Modernization Agent (`sv1657_modernization_PROMPT.md`)

The first agent performs the initial modernization of SV1657 text into contemporary Dutch. Key characteristics:

- **Input**: Original SV1657 text (with Hebrew/Greek source text) + NBV21 translation for reference
- **Goal**: "Renovation, not retranslation" - preserve the distinctive character of the Statenvertaling while modernizing grammar and archaic vocabulary
- **Approach**: Uses NBV21 for inspiration on natural contemporary phrasing and proper names, but never copies literally (NBV21 uses different source texts and translation principles)
- **Output**: Modernized text with all annotations and biblical references preserved

### 2. Linguistic Review Agent (`neerlandicus_review_PROMPT.md`)

The second agent acts as a Dutch linguist, reviewing the modernized text for naturalness and fluency:

- **Focus areas**: Detecting remaining archaisms, unnatural syntax, overly formal phrasing, outdated idioms, and readability issues
- **Goal**: Ensure the text reads as natural, contemporary Dutch without sacrificing the literary character
- **Output**: Refined text with linguistic improvements

### 3. Editorial Review Agent (`editor_PROMPT.md`)

The final agent performs authoritative editorial review with expertise in Biblical Hebrew (BHS) and Koine Greek (Textus Receptus):

- **Primary duty**: Verify fidelity to source texts - ensuring tense, mood, voice, and lexical choices remain accurate
- **Critical tasks**:
  - Correct biblical reference errors (a common issue in earlier stages)
  - Preserve all annotations and properly position them in restructured sentences
  - Maintain inserted words marked with `[]` from the original Statenvertaling
- **Balance**: Maintain both source text fidelity and modern Dutch fluency
- **Output**: Final, authoritative text ready for publication

### Design Philosophy

This multi-agent approach separates concerns:

1. **Modernization** focuses on making text accessible
2. **Linguistic review** ensures natural contemporary Dutch
3. **Editorial review** guarantees theological and textual accuracy

Each agent acts as a check on the previous stage, reducing the risk of errors that might occur in a single-pass approach.
