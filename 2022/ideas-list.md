# ⚡ Important information for interested students  ⚡
- Read the [get started page of GSoC2022](https://summerofcode.withgoogle.com/get-started/)
- Remember that Gridap participates in GSoC2022 with [NumFOCUS](https://numfocus.org/) as umbrella organization.
- Read this ideas page carefully
- Think on how you can contribute to the Gridap project based on this ideas page, your expertise, and your interests
- Contact us before applying via our [Gitter chat](https://gitter.im/Gridap-jl/community) to find a suitable topic for your proposal
- Ask any questions you have on the application process [on this issue](https://github.com/gridap/GSoC/issues/6)

# Gridap.jl

[Gridap.jl](https://github.com/gridap/Gridap.jl) is a new generation, open-source, finite element (FE) library implemented in the Julia programming language. Gridap.jl aims at adopting a more modern programming style than existing FE applications written in C/C++ or Fortran.  The library is currently able to solve linear and nonlinear partial differential equations (PDEs) for scalar and vector fields, single and multi-field problems, conforming and nonconforming FE discretizations, on structured and unstructured meshes of simplices and n-cubes. Gridap is extensible and modular. One can implement new FE spaces, new reference elements, use external mesh generators, linear solvers, post-processing tools, etc. See, e.g., the list of available Gridap plugins.


## Mentors

In alphabetical order
- [Santiago Badia](https://github.com/santiagobadia)
- [Oriol Colomés](https://github.com/oriolcg)
- [Alberto F. Martín](https://github.com/amartinhuertas)
- [Eric Neiva](https://github.com/ericneiva)
- [Francesc Verdugo](https://github.com/fverdugo)

## Project ideas

### Add support for adaptive mesh refinement with hanging-nodes to Gridap.jl.

Adaptive mesh refinement (AMR) is a numerical tool used to efficiently exploit computational resources in problems requiring different mesh resolutions at different parts of the computational domain. Octree (resp. quadtree) based mesh generators such a [p4est](https://www.p4est.org/) are among the most efficient ways to generate 3D (resp. 2D) adaptive computational grids. The resulting meshes contain so-called hanging or irregular nodes, i.e., nodes that sit at the edges or faces of coarser neighbor cells. In this case, generating a cell-conforming global numeration of nodes (or degrees of freedom) is not enough to generate a continuous finite element (FE) interpolation. For these reasons, FE codes need to introduce special techniques to impose continuous interpolations at hanging nodes. E.g., this can be done by imposing supplementary linear constraints to the interpolation space. The goal of this project will be to implement a mechanism to handle meshes with hanging-nodes in the Gridap.jl package. To this end, we plan to add new data structures to keep track of hanging nodes, and to build the associated linear constraints from them. Once the constraints are defined, they can easily be imposed to the interpolation space using functions already present in the library, such as the `FESpaceWithLinearConstraints` type. In addition, we already provide wrappers to p4est in the extension package [GridapP4est](https://github.com/gridap/GridapP4est.jl). Thus, the implementation of hanging-node support in Gridap.jl should be feasible within a Google summer of code project. The main tasks of the student will be to become familiar with the geometry-related data structures of Gridap.jl, to extend them according to the project objectives, to release the resulting code via a PR to the main branch of the Gridap.jl project, and to showcase the application of the new feature with examples (e.g., in a new tutorial in our [Tutorials](https://gridap.github.io/Tutorials/dev/) page.)


| **Priority** | **Intensity** | **Project type** | **Goal**  | **Mentors** |
| ------------ | ------------- | ---------------- | --------- | ----------- |
|  High  | Moderate | Long or short depending on student expertise | Implement hanging-node support in Gridap.jl. Develop, document, and open a PR against the master branch of Gridap.jl. |  [Francesc Verdugo](https://github.com/fverdugo), [Alberto F. Martin](https://github.com/amartinhuertas) and [Eric Neiva](https://github.com/ericneiva)

### Advanced visualization of finite element simulations in Julia with GridapMakie.jl.
The visualization of numerical results is an important part of finite element (FE) computations. It is a vital tool to inspect the computed solutions either for debugging purposes or to generate publication-ready quality images and animations. The conventional way of visualizing data resulting from FE simulations in Gridap.jl is to write vtu files to disk and use [Paraview](https://www.paraview.org/) to visualize them. This allows one to leverage the excellent and feature-rich visualization capabilities of Paraview, but it poses challenges when it comes to inspect data visually from Julia code directly or to manipulate it with packages of the Julia open-source package ecosystem. For this reason, in the last edition of Google summer of code, we developed a first release of [GridapMakie.jl](https://github.com/gridap/GridapMakie.jl), a package for the visualization of Gridap.jl data structures using [Makie.jl](https://github.com/JuliaPlots/Makie.jl). This first release, provides support for visualization of scalar fields on computational meshes of triangular and tetrahedral elements and provides also reactive *plot recipies* that allow one to easily generate interactive plots and animations. This functionality already accounts for an important share of the visualization needs in FE computations, but several important features are still missing. In this new, project we plan to enrich GridapMakie.jl with new visualization tools such as support for quadrilateral and hexahedral elements, the visualization of vector-values fields, clipping and slicing of computational grids, etc. We also want to improve the user experience, when generating interactive plots in Jupyter or [Pluto.jl](https://github.com/fonsp/Pluto.jl) notebooks, and VSCode side panels. This work will result in a second release of GridapMakie.jl with the new features. The main role of the GSoC student will be to further develop GridapMakie.jl, document it and, finally, release it in the official [Julia package registry](https://github.com/JuliaRegistries/General).

| **Priority** | **Intensity** | **Project type** | **Goal**  | **Mentors** |
| ------------ | ------------- | ---------------- | --------- | ----------- |
|  Medium  | Moderate | Long or short  | Implement advanced visualization techniques in GridapMakie.jl. Develop, document and release a new version the GridapMakie.jl package. |  [Francesc Verdugo](https://github.com/fverdugo)

### Discretisation techniques on general polytopes 

The numerical approximation of PDEs using finite element and finite volume methods relies on the definition of a mesh of the domain of interest. These meshes are in general composed of _cells_, which are  triangles/tetrahedra or quadrilaterals/hexahedra. The mesh generation step is one of the bottlenecks in the PDE discretisation workflow, since it is hard to automatise and parallelise. In order to alleviate the situation, some numerical discretisation schemes (discontinuous Galerkin, hybridisable methods) provide flexibility in the mesh generation because they can be defined for any cell topology. `Gridap` provides Discontinuous Galerkin methods in the main package and hybridisable ones in `GridapHybrid`. However, these implementations cannot exploit yet general polytopes. In this project, we want to provide this extra functionality. First, we will exploit a general representation of polytopes as _rotation systems_, i.e., a sub-type of graphs. We will define a concrete `Polytope` with a graph representation in which the adjacency of each vertex is a _cyclic order_ and define its API based on such description. Next, we will implement a new `Quadrature` rule that will work on general polytopes (see, e.g., [here](http://dilbert.engr.ucdavis.edu/~suku/quadrature/hni-curvedsolid.pdf)). Finally, some polytopal meshes will be used to check the implementations on discontinuous Galerkin and hybridised solvers. If the project type is _long_, we will also explore the implementation of other schemes that work on polytopal meshes, e.g., virtual element methods or hybrid high order methods.

| **Priority** | **Intensity** | **Project type** | **Goal**  | **Mentors** |
| ------------ | ------------- | ---------------- | --------- | ----------- |
|  Medium  | Moderate | Long or short depending on student expertise | Implement general polytopes and quadratures in `Gridap.jl`. Combine them with DG and hybridised methods in `Gridap.jl` and `GridapHybrid.jl`. | [Santiago Badia](https://github.com/santiagobadia), [Alberto F. Martin](https://github.com/amartinhuertas) and [Eric Neiva](https://github.com/ericneiva)


### Adjoint-based PDE-constrained optimization

In many engineering and scientific applications there is the need to find solutions to optimization problems where the variables are constrained by certain PDEs. That is the case of inverse problems where one is interested in finding the optimal set of parameters such that the solution matches with observations, or design optimization problems where one wants to find the optimal parameter that maximizes or minimizes a quantity of interest. Most efficient optimization solvers rely on the derivative of the optimization functional with respect to the parameters, which can be obtained from the adjoint of the forward problem. One of the major challenges appears when dealing with transient PDEs and time-dependent parameters. In that case, the forward problem is integrated forward in time and stored in memory so that it can be used by the adjoint problem that is solved backwards. In this project we propose to create a general framework to compute adjoints, and use them in optimization problems, using `Gridap.jl` and `GridapODEs.jl` as a solvers for the forward problem. The goal is to take advantage of Automatic Differentiation capabilities of *Julia* to automate the optimization process. The student working on this project will first start with the definition of a general API for optimization problems using discrete adjoints of steady forward problems. Next, we will work in forward/backward time marching schemes for adjoints in transient problems. Finally, we will implement checkpointing schemes to limit the memory consumption in the computation of adjoints of time-dependent problems.

| **Priority** | **Intensity** | **Project type** | **Goal**  | **Mentors** |
| ------------ | ------------- | ---------------- | --------- | ----------- |
|  Medium  | Moderate | Long or short depending on student expertise | Create a general framework to compute adjoints, and use them in optimization problems, using `Gridap.jl` and `GridapODEs.jl` as a solvers for the forward problem. | [Oriol Colomés](https://github.com/oriolcg) and [Francesc Verdugo](https://github.com/fverdugo)
