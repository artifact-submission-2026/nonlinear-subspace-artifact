# Nonlinear Subspace Artifact

This repository contains anonymous research artifacts supporting the constructions discussed in the manuscript.

## Files for Sect. 3.1

### `sec3_1_parametric_macaulay_example.sage`

This SageMath script reproduces the parametric Macaulay matrix example discussed in Sect. 3.1 of the paper. The example is carried out over the KoalaBear prime field

\[
p = 2^{31}-2^{24}+1 = 2130706433,
\]

with state width \(t=5\) and S-box exponent \(\alpha=3\).

The detailed modeling procedure is described in Sect. 3.1 of the paper.

### `sec3_1_subspace_path_parameters_solving.tex`

This file records the concrete solution data for the Sect. 3.1 example. It contains:

- the field and state parameters;
- the solved parameter values;
- the Cauchy MDS matrix;
- the round constants used in the example.

Its contents correspond to the concrete instance reported in Auxiliary Supporting Material A of the paper.

## Files for Sect. 3.3

### `sec3_3_nonlinear_subspace_construction.sage`

This SageMath script verifies a concrete nonlinear subspace trail instance based on the construction in Sect. 3.3 of the paper.

The instance is motivated by the 2026 Poseidon cryptanalysis bounty setting for Poseidon-31. It uses:

- the KoalaBear prime field
  \[
  p = 2^{31}-2^{24}+1 = 2130706433;
  \]
- state width \(t=16\);
- S-box exponent \(\alpha=3\);
- the CICO-2 setting corresponding to the Poseidon-31 bounty target.

The goal of the script is to verify an internal round nonlinear subspace construction for this CICO-2 setting. The MDS matrix and round constants are sampled over the base field. The MDS matrix is chosen to satisfy the no-invariant-subspace-trail condition considered in the paper.

The modeling strategy follows Sect. 3.3 of the manuscript.

### `sec3_3_subspace_path_polynomials.tex`

This file records the explicit nonlinear subspace trail constructed for the Sect. 3.3 instance. It includes the polynomial expressions for the intermediate states, the nonlinear source terms, and the resulting subspace path data.

The listed construction gives a nonlinear trail through 29 internal partial rounds.# nonlinear-subspace-artifact
Anonymous research artifacts for a cryptanalysis manuscript. This repository contains verification code, concrete parameter instances, and polynomial data supporting the constructions discussed in the paper.
