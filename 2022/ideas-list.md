# ⚡ Important information for interested students  ⚡
- Read the [get started page of GSoC2022](https://summerofcode.withgoogle.com/get-started/)
- Remember that Gridap participates in GSoC2022 with [NumFOCUS](https://numfocus.org/) as umbrella organization.
- Read this ideas page carefully
- Think on how you can contribute to the Gridap project based on this ideas page, your expertise, and your interests
- Contact us before applying via our [Gitter chat](https://gitter.im/Gridap-jl/community) to find a suitable topic for your proposal
- Ask any questions you have on the application process [on this issue](https://github.com/gridap/GSoC/issues)

# Gridap.jl

[Gridap.jl](https://github.com/gridap/Gridap.jl) is a new generation, open-source, finite element (FE) library implemented in the Julia programming language. Gridap.jl aims at adopting a more modern programming style than existing FE applications written in C/C++ or Fortran.  The library is currently able to solve linear and nonlinear partial differential equations (PDEs) for scalar and vector fields, single and multi-field problems, conforming and nonconforming FE discretizations, on structured and unstructured meshes of simplices and n-cubes. Gridap is extensible and modular. One can implement new FE spaces, new reference elements, use external mesh generators, linear solvers, post-processing tools, etc. See, e.g., the list of available Gridap plugins.


## Mentors

In alphabetical order
- [Santiago BADIA](https://github.com/santiagobadia)
- [Oriol COLOMÉS](https://github.com/oriolcg)
- [Alberto F. MARTÍN](https://github.com/amartinhuertas)
- [Eric NEIVA](https://github.com/ericneiva)
- [Francesc VERDUGO](https://github.com/fverdugo)

## Project ideas

### Advanced visualization of finite element simulations in Julia with GridapMakie.jl.
The visualization of numerical results is an important part of finite element (FE) computations. It is a vital tool to inspect the computed solutions either for debugging purposes or to generate publication-ready quality images and animations. The conventional way of visualizing data resulting from FE simulations in Gridap.jl is to write vtu files to disk and use [Paraview](https://www.paraview.org/) the visualize them. This allows one to leverage the excellent and feature-rich visualization capabilities of Paraview, but it posses challenges when it comes to inspect data visually from Julia code directly or to manipulate it with packages of the Julia open-source package ecosystem. For this reason, in the last edition of Google summer of code, we developed a first release of [GridapMakie.jl](https://github.com/gridap/GridapMakie.jl), a package for the visualization of Gridap.jl data structures using [Makie.jl](https://github.com/JuliaPlots/Makie.jl). This first release, provides support for visualization of scalar fields on computational meshes of triangular and tetrahedral elements and provides also reactive *plot recipies* that allow one to easily generate interactive plots and animations. This functionality already accounts for an important share of the visualization needs in FE computations, but several important features are still missing. In this new, project we plan to enrich GridapMakie.jl with new visualization tools such as support for quadrilateral and hexahedral elements, the visualization of vector-values fields, clipping and slicing of computational grids, etc. We also want to improve the user experience, when generating interactive plots in Jupyter or [Pluto.jl](https://github.com/fonsp/Pluto.jl) notebooks, and VSCode side panels. This work will result in a second release of GridapMakie.jl with the new features. The main role of the GSoC student will be to further develop GridapMakie.jl, document it and, finally, release it in the official [Julia package registry](https://github.com/JuliaRegistries/General).

| **Intensity** | **Project type** | **Priority** | **Goal**  | **Mentors** |
| ------------- | ---------------- | ------------ | --------- | ----------- |
| Moderate | Long or short  |  Medium  | Implement advanced visualization techniques in GridapMakie.jl. Develop, document and release a new version the GridapMakie.jl package. |  [Francesc VERDUGO](https://github.com/fverdugo)


