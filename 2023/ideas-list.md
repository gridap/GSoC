# ⚡ Important information for interested students  ⚡
- Read the [GSoC 2023 page](https://summerofcode.withgoogle.com/)
- Remember that Gridap participates in GSoC with [NumFOCUS](https://numfocus.org/) as umbrella organization.
- Read this ideas page carefully
- Think on how you can contribute to the Gridap project based on this ideas page, your expertise, and your interests
- Contact us before applying via our [Gitter chat](https://gitter.im/Gridap-jl/community) to find a suitable topic for your proposal
- Ask any questions you have on the application process [on this issue](https://github.com/gridap/GSoC/issues/10)

# Gridap.jl

[Gridap.jl](https://github.com/gridap/Gridap.jl) is a new generation, open-source, finite element (FE) library implemented in the Julia programming language. Gridap.jl aims at adopting a more modern programming style than existing FE applications written in C/C++ or Fortran.  The library is currently able to solve linear and nonlinear partial differential equations (PDEs) for scalar and vector fields, single and multi-field problems, conforming and nonconforming FE discretizations, on structured and unstructured meshes of simplices and n-cubes. Gridap is extensible and modular. One can implement new FE spaces, new reference elements, use external mesh generators, linear solvers, post-processing tools, etc. See, e.g., the list of available Gridap plugins.


## Mentors

In alphabetical order
- [Oriol Colomés](https://github.com/oriolcg)
- [Francesc Verdugo](https://github.com/fverdugo)

## Project ideas

### Adjoint-based PDE-constrained optimization

In many engineering and scientific applications there is the need to find solutions to optimization problems where the variables are constrained by certain PDEs. That is the case of inverse problems where one is interested in finding the optimal set of parameters such that the solution matches with observations, or design optimization problems where one wants to find the optimal parameter that maximizes or minimizes a quantity of interest. Most efficient optimization solvers rely on the derivative of the optimization functional with respect to the parameters, which can be obtained from the adjoint of the forward problem. One of the major challenges appears when dealing with transient PDEs and time-dependent parameters. In that case, the forward problem is integrated forward in time and stored in memory so that it can be used by the adjoint problem that is solved backwards. In this project we propose to create a general framework to compute adjoints, and use them in optimization problems, using `Gridap.jl` and `GridapODEs.jl` as a solvers for the forward problem. The goal is to take advantage of Automatic Differentiation capabilities of *Julia* to automate the optimization process. The student working on this project will first start with the definition of a general API for optimization problems using discrete adjoints of steady forward problems. Next, we will work in forward/backward time marching schemes for adjoints in transient problems. Finally, we will implement checkpointing schemes to limit the memory consumption in the computation of adjoints of time-dependent problems.

| **Priority** | **Intensity** | **Project type** | **Goal**  | **Mentors** |
| ------------ | ------------- | ---------------- | --------- | ----------- |
|  Medium  | Moderate | Long (~350hr) or Medium (~175hr) depending on student expertise | Create a general framework to compute adjoints, and use them in optimization problems, using `Gridap.jl` and `GridapODEs.jl` as a solvers for the forward problem. | [Oriol Colomés](https://github.com/oriolcg), [Santiago Badia](https://github.com/santiagobadia) and [Francesc Verdugo](https://github.com/fverdugo)
