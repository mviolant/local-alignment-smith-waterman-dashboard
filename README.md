# Smith–Waterman Local Sequence Alignment Dashboard

An interactive browser-based dashboard for exploring **local pairwise sequence alignment** using the Smith–Waterman dynamic programming algorithm.

The tool allows users to enter two biological sequences, modify alignment scoring parameters, inspect the dynamic programming matrix, and examine the resulting optimal local alignment.

🔗 **Live Demo:**  
https://mviolant.github.io/local-alignment-smith-waterman-dashboard/

## Overview

Smith–Waterman alignment identifies the highest-scoring local region shared between two sequences rather than forcing an alignment across their entire lengths.

This dashboard was developed as part of my graduate bioinformatics coursework to explore how dynamic programming, scoring systems, gap penalties, and traceback decisions affect sequence alignment results.

## Features

- Smith–Waterman local sequence alignment
- Interactive sequence input
- Dynamic programming scoring matrix
- User-defined:
  - Match score
  - Mismatch penalty
  - Gap-opening penalty
  - Gap-extension penalty
- Affine gap penalties
- Traceback from the highest-scoring cell to a zero-valued cell
- Optimal local alignment display
- Alignment score
- Alignment coordinates within the original sequences
- Sequence-length reporting
- Per-cell scoring information
- Deterministic traceback handling for ties
- Input validation for biological sequence characters

## Alignment Method

For local alignment, the first row and first column of the scoring matrix are initialized to zero.

Each matrix cell considers possible alignment paths including:

- diagonal movement for a match or mismatch
- horizontal movement for a gap
- vertical movement for a gap
- zero, allowing a new local alignment to begin

The highest-scoring cell represents the end of the optimal local alignment.

Traceback proceeds from this cell until a score of zero is reached.

## Affine Gap Penalties

The dashboard supports affine gap penalties, where opening a gap is penalized differently from extending an existing gap.

Conceptually:

```text
gap cost = gap opening penalty + gap extension penalty × additional gap positions
```

## Example Comparison

Consider:

```text
Sequence X: TTCATA
Sequence Y: TGCTCGTA

Match: +5
Mismatch: -2
Gap: -6
```

A local alignment identifies the highest-scoring matching subsequences rather than requiring the complete sequences to align.

## Example optimal local region:

TCATA
TCGTA

with coordinates corresponding to the aligned portions of the original sequences.

## Technologies

- HTML
- CSS
- JavaScript
- Git / GitHub
- GitHub Pages

## Project Context

Developed as part of graduate-level coursework in **Bioinformatics and Genomics at UNC Charlotte.**

The dashboard is intended as an educational visualization of pairwise sequence alignment rather than a replacement for production bioinformatics software such as BLAST, EMBOSS Water, or other optimized alignment tools.

## Author

**Maria Violante**  
M.S. Bioinformatics Candidate  
UNC Charlotte

GitHub: https://github.com/mviolant
