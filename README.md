# Nonlinear Subspace Artifact

This repository contains anonymous research artifacts supporting the nonlinear
subspace constructions discussed in the manuscript.

The artifacts include SageMath Jupyter notebooks, concrete parameter instances,
and explicit polynomial data for the examples in Sections 3.1 and 3.3 of the
paper.

## Environment

The verification code is provided as Jupyter notebooks and was written and
tested with **SageMath 9.5** using the SageMath Jupyter kernel. The notebooks
are not plain Python notebooks.

To run the notebooks, start Jupyter from SageMath, for example by

```bash
sage -n jupyter
```

and then open the corresponding `.ipynb` files with the SageMath kernel.

Some helper routines and diagnostic outputs were originally developed during
exploratory computations. In particular, a small amount of non-English comments
or intermediate diagnostic text may remain in auxiliary helper sections. This
does not affect execution. The main verification steps are marked by section
headings in the corresponding notebooks.

## Files for Section 3.1

### `sec3_1_parametric_macaulay_example.ipynb`

This SageMath notebook reproduces the parametric Macaulay matrix example
discussed in Section 3.1 of the paper. The example is carried out over the
KoalaBear prime field

\[
p = 2^{31}-2^{24}+1 = 2130706433,
\]

with state width \(t=5\), S-box exponent \(\alpha=3\), and \(c=d=1\). In this
example, \(Ec=3\). The polynomial path contains one explicitly given linear
constraint \(f_1\) and two nonlinear constraints \(f_2,f_3\). The computation
verifies the ideal-membership relation behind

\[
\langle f_1,f_2\rangle = \langle f_1,f_2,f_3\rangle .
\]

The notebook is organized into four parts:

1. helper routines;
2. parametric Macaulay matrix construction and solving;
3. verification of the nonlinear subspace path.
4. export of the explicit polynomial path.

The detailed modeling procedure is described in Section 3.1 of the paper.

### `sec3_1_subspace_path_parameters_solving.tex`

This file records the concrete solution data for the Section 3.1 example. It
contains:

- the field and state parameters;
- the solved parameter values;
- the Cauchy MDS matrix;
- the round constants used in the example.

Its contents correspond to the concrete instance reported in Auxiliary
Supporting Material A of the paper.

## Files for Section 3.3

### `sec3_3_nonlinear_subspace_construction.ipynb`

This SageMath notebook verifies a concrete nonlinear subspace trail instance
based on the construction in Section 3.3 of the paper.

The instance is motivated by the 2026 Poseidon cryptanalysis bounty setting for
Poseidon-31. It should be understood as a verification of the internal round
nonlinear subspace construction, rather than as a full attack on the complete
challenge instance.

The instance uses:

- the KoalaBear prime field
  \[
  p = 2^{31}-2^{24}+1 = 2130706433;
  \]
- state width \(t=16\);
- S-box exponent \(\alpha=3\);
- the CICO-2 constraint pattern, where two input coordinates and two output
  coordinates are fixed.

In this setting, the available number of extra constraints for the internal
round construction is

\[
E_c = t-4 = 12.
\]

The goal of the notebook is to construct and verify an internal round nonlinear subspace
trail for this CICO-2 setting. The MDS matrix and round constants are
sampled over the base field. The MDS matrix is chosen to satisfy the
no-invariant-subspace-trail condition considered in the paper.

The notebook is organized into four parts:

1. helper routines;
2. construction of the nonlinear subspace path;
3. verification of the constructed ideal;
4. reconstruction and export of the explicit polynomial path.

The main verification part checks the relevant ideal degeneration
properties. The final export part reconstructs the explicit nonlinear
polynomial path in the same way and records it in the accompanying TeX file.

### `sec3_3_subspace_path_polynomials.tex`

This file records the explicit nonlinear subspace trail constructed for the
Section 3.3 instance. It includes:

- the field and state parameters;
- the round constants;
- the Cauchy MDS matrix;
- the relations among the \(u_i\);
- the derived expression \(u_{25}\);
- the reduced state records along the polynomial path.

The listed construction gives a nonlinear trail through 25 internal partial
rounds.

## Notes

The notebooks are intended as supplementary verification artifacts rather than
as a standalone software package. They are provided to make the concrete
computations and polynomial data inspectable and reproducible.

The TeX files are generated records of the concrete instances and are included
for convenient inspection of the solved parameters and polynomial paths.
