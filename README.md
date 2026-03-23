# COMP 527 Final Project: Extending First-Order Logic with Lists and Recursion

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/youhome3502/527_final_extend_FOL)](https://github.com/youhome3502/527_final_extend_FOL/stargazers)

This project extends a Natural Deduction-based First-Order Logic (FOL) system with inductive data types and structural recursion, following ideas from Godel's System T.

We focused on modeling **lists** and **recursive functions** over lists in a way that supports both formal proofs and implementation in Beluga.

## Consent & Authorship

Team Members:
- Anthony Beaudry (261056660)
- Tommy Zhou (260913606)
- Claire Yang (260898597)

Contributions:

Every one of us contributed to the project. Anthony mainly focused on the functions and properties of the system, Tommy mainly focused on the syntax and semantics of the system, and Claire mainly focused on the formalization of the system in Beluga.

**All team members consent to making this project public and allowing it to be shared on Ed for other students to reference.**


## Project Deliverables

- **`COMP527_Abstract.pdf`**
  - Two-page extended abstract (excluding biography)
  - Outlines:
    - Project motivation and Related work
    - Our proposed approach and formalization plan
    - Team member responsibilities and contribution breakdown

- **`COMP527_Artifacts.pdf`**
  - Technical artifact documentation
  - Includes:
    - Summary of logic definitions and Beluga syntax
    - Formal proofs: equality, length, append
    - Induction schema explanations
    - Soundness and completeness discussions
    - Notes on encoding natural numbers via lists

- **`COMP527_project_slides.pdf`**
  - Slides for the 10-minute [presentation video](https://youtu.be/WuVoTgnJytY).

- **`extend_fol_list.bel`**
  - Core system: FOL + list + recursion
  - Defines:
    - Inductive list type (`nil`, `cons`)
    - System-T style recursion operator `list_rec`
    - Logical relations: `append`, `length`, and `eqList`
    - Natural deduction rules extended to handle those
  - Contains:
    - List induction schema
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


## Dependencies

This project requires:
- [Beluga](https://github.com/Beluga-prover/beluga) - A proof assistant for reasoning about formal systems
- OCaml 4.08+

### Installation

```bash
# Install Beluga
git clone https://github.com/Beluga-prover/beluga.git
cd beluga
make
```

### Running

```bash
# Load the FOL with lists extension
beluga extend_fol_list.bel

# Or try the natural numbers + lists version
beluga extend_fol_nat_list.bel
```

## Video Presentation

We present our key ideas in the video below:

[Youtube Link](https://youtu.be/WuVoTgnJytY)


## Core Contributions
- List-based recursion modeled via `list_rec` (System T style)
- Inductive schema over lists for formal proofs
- Constructive examples type-checked in Beluga

## License

This project is for educational purposes (COMP 527 course project). The code is licensed under MIT License - see [LICENSE](LICENSE) file for details.

## Citation

If you use this project in your work, please cite:

```
@software{comp527_fol_lists,
  title = {Extending First-Order Logic with Lists and Recursion},
  authors = {Anthony Beaudry and Tommy Zhou and Claire Yang},
  year = {2024},
  course = {COMP 527},
  institution = {McGill University},
  url = {https://github.com/youhome3502/527_final_extend_FOL}
}
```
