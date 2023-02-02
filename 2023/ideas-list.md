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
- [Francesc Verdugo](https://github.com/fverdugo)

## Project ideas

### Simplify the usage of distributed sparse linear solvers

Large finite element computations based on Gridap can be deployed in distributed-memory parallel computers using GridapDistributed. The high level user API of the parallel codes based on GridapDistributed is almost equivalent to the one of Gridap. So, one can easily switch from a serial computation using Gridap to a parallel one using GridapDistributed. At least, this is what the theory says. In practice, the transition from a serial driver to a parallel one is not that obvious. The default sparse linear solver used to solve the discrete finite element system is not parallel at this moment. It just gathers the distributed system matrix and the right hand side vector into the main process and performs a serial solve using the Julia functions `\` (back-slash) or `lu`. This means that the user will never get parallel scaling in the solver phase which is often the main bottleneck in the simulation. To circumvent this, one can use all the plethora of distributed sparse linear solvers available in PETSc via the bindings in GridapPETSc, but it is not always very convenient. It requires advanced knowledge of PETSc, which has a remarkable learning curve and often requires to manually configure, compile, and install PETSc on the cluster in other to use specific solver types. Having to deal with PETSc makes considerably hard the transition from a serial Gridap computation to a parallel one. To fix this problem, we plan to equip GridapDistributed with a new default linear solver that is able to solve the problem in parallel. To this end, we plan to interface with existing distributed sparse linear solvers like MUMPS and SuperLU_Dist which will allow to solve a wide variety of problem types in a robust manner, at least for moderate problem sizes. For really advanced simulations, one can still use PETSc, but we want to reserve this for advanced users. This GSoC project will mainly consist in overloading functions `\` and `lu` in PartitionedArrays (the distributed linear algebra back-end of GridapDistributed) with parallel implementations based on MUMPS or SuperLU_Dist.

| **Priority** | **Intensity** | **Project type** | **Goal**  | **Mentors** |
| ------------ | ------------- | ---------------- | --------- | ----------- |
|  High  | Moderate | Long (~350hr) or Medium (~175hr) depending on student expertise | Provide a default distributed sparse linear solver to GridapDistributed and PartitionedArrays | [Francesc Verdugo](https://github.com/fverdugo)


