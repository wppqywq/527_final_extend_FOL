# COMP 527 Final Project: Extending First-Order Logic with Lists and Recursion

This project extends a Natural Deduction-based First-Order Logic (FOL) system with inductive data types and structural recursion, following ideas from Godel's System T.

We focused on modeling **lists** and **recursive functions** over lists in a way that supports both formal proofs and implementation in Beluga.

## Consent & Authorship

Team Members:
- Anthony Beaudry (261056660)
- Tommy Zhou (260913606)
- Claire Yang (260898597)

Contributions:
- Anthony Beaudry: Project planning, report wirting (**To Be Specified**)
- Tommy Zhou: Focused on the syntax and semantics of the system, as well as the notes-style artifact
- Claire Yang: Beluga implementation, example theorems.

**All team members consent to making this project public and allowing it to be shared on Ed for future students to reference.**

## File Structure

- **`extend_fol_list.bel`**
  - Core system: FOL + list + recursion
  - Defines:
    - Inductive list type (`nil`, `cons`)
    - System-T style recursion operator `list_rec`
    - Logical relations: `append`, `length`, and `eqList`
    - Natural deduction rules extended to handle those
  - Contains:
    - List induction schema (`list_ind_schema`)
    - Recursive proofs for:
      - `append(l, nil) = l`
      - `length(cons a nil) = cons a nil`
      - `list_rec` usage examples
    - Several example proofs (both quantified and concrete)
    - (Some higher-level proofs simplified using `⊤I` as placeholders due to complexity in beluga.)

- **`extend_fol_nat_list.bel`**
  - Initial version of the system, went a little ahead with `nat`, so we do something like: `add(n, 0) = n` and `length(append(l1, l2)) = add(length l1, length l2)`.
  - Includes:
    - `nat` type with constructors `z`, `suc`
    - Relation `add`, with basic example proofs
  - Preserved for reference and optional future use


## Core Contributions
- List-based recursion modeled via `list_rec` (System T style)
- Inductive schema over lists for formal proofs
- Constructive examples type-checked in Beluga

## Video Presentation
We present our key ideas in the video below:

[Youtube Link](https://youtu.be/WuVoTgnJytY)
