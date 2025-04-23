# COMP 527 Final Project: Extending First-Order Logic with Lists and Recursion

This project extends a Natural Deduction-based First-Order Logic (FOL) system with **inductive data types** and **structural recursion**, following ideas from Godel's System T.

We focused on modeling **lists** and **recursive functions over lists** in a way that supports both formal proofs and implementation in Beluga.

## File Structure

### `extend_fol_list.bel`
- Core system: FOL + list + recursion (list-only version)
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
  - (Some higher-level proofs still simplified using `⊤I` as placeholders)

### `extend_fol_nat_list.bel`
- Initial version of the system with **both `nat` and `list`** (with simplified proofs, not fully completed)
- Went a little ahead and added `nat` alongside `list`, so we could model arithmetic properties like:
  - `add(n, 0) = n`
  - `length(append(l1, l2)) = add(length l1, length l2)`
- Includes:
  - `nat` type with constructors `z`, `suc`
  - Relation `add`, with basic example proofs
  - Preserved for reference and optional future use

## Core Contributions
- List-based recursion modeled via `list_rec` (System T style)
- Inductive schema over lists for formal proofs
- Constructive examples type-checked in Beluga
- (Optional `nat` extension demonstrates flexibility of the system)

## Authors
- Anthony Beaudry  
- Tommy Zhou  
- Claire Yang
