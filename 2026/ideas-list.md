# ⚡ Important information for interested students  ⚡
- Read the [GSoC 2026 page](https://summerofcode.withgoogle.com/)
- Remember that Gridap participates in GSoC with [NumFOCUS](https://numfocus.org/) as umbrella organization.
- Read this ideas page carefully
- Think on how you can contribute to the Gridap project based on this ideas page, your expertise, and your interests
- Contact us before applying to find a suitable topic for your proposal (see contact details in the subsection "mentors" below)
- Ask any questions you have on the application process [on this issue](https://github.com/gridap/GSoC/issues/18)

# Gridap.jl

[Gridap.jl](https://github.com/gridap/Gridap.jl) is a new generation, open-source, finite element (FE) library implemented in the Julia programming language. Gridap.jl aims at adopting a more modern programming style than existing FE applications written in C/C++ or Fortran.  The library is currently able to solve linear and nonlinear partial differential equations (PDEs) for scalar and vector fields, single and multi-field problems, conforming and nonconforming FE discretizations, on structured and unstructured meshes of simplices and n-cubes. Gridap is extensible and modular. One can implement new FE spaces, new reference elements, use external mesh generators, linear solvers, post-processing tools, etc. See, e.g., the list of available Gridap plugins.

## Mentors

In alphabetical order
- [Eric Neiva](https://github.com/ericneiva)
- [Martina Gatti](https://github.com/martinagatti)
- [Nicholas Mueller](https://github.com/nichomueller)
- [Oriol Colomés](https://github.com/oriolcg)

## Project ideas

### Reduced order modelling with neural operators

Numerical simulation of partial differential equations (PDEs) is a cornerstone of scientific computing, but remains computationally expensive when many-query evaluations are required, such as in parameter studies, inverse problems, or real-time applications. In this project, we propose the student to design and implement a general framework for extracting reduced order models (ROMs) based on neural operators that are trained with finite element method (FEM) solutions generated with Gridap.jl. The project will leverage the rich Julia package ecosystem, combining Gridap.jl, NeuralOperators.jl, GridapROMs.jl, among others.

| **Priority** | **Intensity** | **Project type** | **Goal**  | **Mentors** |
| ------------ | ------------- | ---------------- | --------- | ----------- |
|  High  | Moderate | Medium (~175hr) | Reduced order models with neural operators in Gridap.jl | [Eric Neiva](https://github.com/ericneiva), [Martina Gatti](https://github.com/martinagatti), [Nicholas Mueller](https://github.com/nichomueller) and [Oriol Colomés](https://github.com/oriolcg) |

## AI disclosure policy

All GSoC-related issues and pull requests must disclose AI usage.

If AI tools were used, end the issue or PR with a sentence beginning:

    AI assistance was used for ...

If no AI tools were used at all, end with the sentence:

    No AI tools were used in this contribution.

Submissions that omit a disclosure may be closed without review.
