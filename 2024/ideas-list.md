# ⚡ Important information for interested students  ⚡
- Read the [GSoC 2024 page](https://summerofcode.withgoogle.com/)
- Remember that Gridap participates in GSoC with [NumFOCUS](https://numfocus.org/) as umbrella organization.
- Read this ideas page carefully
- Think on how you can contribute to the Gridap project based on this ideas page, your expertise, and your interests
- Contact us before applying to find a suitable topic for your proposal (see contact details in the subsection "mentors" below)
- Ask any questions you have on the application process [on this issue](https://github.com/gridap/GSoC/issues/13)

This page is under construction 🔨

# Gridap.jl

[Gridap.jl](https://github.com/gridap/Gridap.jl) is a new generation, open-source, finite element (FE) library implemented in the Julia programming language. Gridap.jl aims at adopting a more modern programming style than existing FE applications written in C/C++ or Fortran.  The library is currently able to solve linear and nonlinear partial differential equations (PDEs) for scalar and vector fields, single and multi-field problems, conforming and nonconforming FE discretizations, on structured and unstructured meshes of simplices and n-cubes. Gridap is extensible and modular. One can implement new FE spaces, new reference elements, use external mesh generators, linear solvers, post-processing tools, etc. See, e.g., the list of available Gridap plugins.

## Mentors

In alphabetical order
- Person 1
- Person 2

## Project ideas

### Leverage Auto-matic differentiation rules in GridapDistributed API and Multi-field Spaces

Auto-matic differentiation helps users generate a fully implicit abstract back-end for computing the jacobians and residuals of the weak-form PDEs, which is very useful especially when the cost of deriving the residuals and jacobians using tradiational approaches like variational formulation and virtual work methods is very expensive. Current Gridap API only supports AD for use cases that involve serial implementation of FEM routines and single field spaces, however, things get complicated in the cases of solving problems that involves multi-scale PDEs and interface coupled multi-physics problems that needs to define multi fields in different domains inside the mesh. Besides, the AD functionality can also be computationally extremely useful in implementing parallel routines under the hood of GridapDistributed API, where the jacobians and residuals can be computed parallely for each of the grid inside the mesh. This process of automating the computation of residuals and jacobians can also be extended in transient state problems as well.

| **Priority** | **Intensity** | **Project type** | **Goal**  | **Mentors** |
| ------------ | ------------- | ---------------- | --------- | ----------- |
|  TBD  | TBD | TBD (~hr) | Extend the Auto-matic differentiation functionality to GridapDistributed API and Multi-field Spaces | [Francesc Verdugo](https://github.com/fverdugo) and [Oriol Colomés](https://github.com/oriolcg)
