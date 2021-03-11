# ⚡ Important information for interested students  ⚡
- Read the [get started page of GSoC2021](https://summerofcode.withgoogle.com/get-started/)
-  Remember that Gridap participates in GSoC2021 via the [NumFOCUS umbrella](https://summerofcode.withgoogle.com/organizations/5765643267211264/)
- Read this ideas page carefully
- Think on how you can contribute to the Gridap project based on this ideas page, your expertise, and your interests
- Contact us before applying via our [Gitter chat](https://gitter.im/Gridap-jl/community)  to find a suitable topic for your proposal

# Gridap.jl

[Gridap.jl](https://github.com/gridap/Gridap.jl) is a new generation, open-source, finite element (FE) library implemented in the Julia programming language. Gridap.jl aims at adopting a more modern programming style than existing FE applications written in C/C++ or Fortran.  The library is currently able to solve linear and nonlinear partial differential equations (PDEs) for scalar and vector fields, single and multi-field problems, conforming and nonconforming FE discretizations, on structured and unstructured meshes of simplices and n-cubes. Gridap is extensible and modular. One can implement new FE spaces, new reference elements, use external mesh generators, linear solvers, post-processing tools, etc. See, e.g., the list of available Gridap plugins.


## Mentors

In alphabetical order
- [Santiago Badia](https://github.com/santiagobadia)
- [Eric Neiva](https://github.com/ericneiva)
- [Francesc Verdugo](https://github.com/fverdugo)
- [Jan Weidner](https://github.com/jw3126)

## Project ideas

### GridapMakie.jl: visualization of Gridap.jl computations in Julia via Makie.jl.

#### Abstract

The visualization of numerical results is an important part of FE computations. It is a vital tool to inspect the computed solutions either for debugging purposes or to generate publication-ready quality images and animations.  The current way of visualizing data from Gridap.jl computations is to write it to disk in vtu format and open the resulting file in [Paraview](https://www.paraview.org/). This allows one to leverage the excellent visualization capabilities of Paraview, but it posses challenges when it comes to inspect data visually from Julia code directly or to manipulate it with packages of the Julia open-source package ecosystem. For this reason, the main objective of this project is to adopt [Makie.jl](https://github.com/JuliaPlots/Makie.jl) as a second visualization back-end for Gridap.jl simulations. Makie.jl is a GPU-accelerated high-level visualization library written in Julia, which enables the generation of publication-ready quality images and animations in different file formats and its interactive visualization within jupyter or [Pluto.jl](https://github.com/fonsp/Pluto.jl) notebooks, and VSCode side panels (see the [Makie.jl examples](https://github.com/JuliaPlots/Makie.jl#examples-from-the-documentation) for further details). The Makie.jl functionality is extensible via so-called *plot recipies*, which allow one to define how user-defined types are visualized. The main task in this project will be to define a set of plot recipes for several types defined in Gridap, with the final goal of visualizing results of Gridap.jl simulations from Julia code directly and benefit from all functionallity of Makie.jl-based visualization. This work will result in the release of the [GridapMakie.jl](https://github.com/gridap/GridapMakie.jl) package, which at this moment contains an incomplete draft implementation of a sub-set of the required recipes that will senve as the starting point. The main role of the GSoC student in this project will be to further develop the GridapMakie.jl package, document it and, finally, release it in the official [Julia package registry](https://github.com/JuliaRegistries/General).

| **Intensity** | **Priority** | **Goal**  | **Mentors**  |
| -------------                          | ------------              | ------------- | -----------              |
| Moderate  |  Medium  | Visualize Gridap.jl simulations in Julia via Makie.jl. Develop, document and release the GridapMakie.jl package. |  [Francesc Verdugo](https://github.com/fverdugo) and [Jan Weidner](https://github.com/jw3126)

#### Helpful Experience

- Basic knowledge of Julia
- Prior work with Gridap.jl
- Prior work with Makie.jl

### GridapFlux.jl: Gridap.jl data-driven applications via Flux.jl

#### Abstract
Data science and numerical approximation of Partial Differential Equations (PDEs) are converging in a wide range of exciting ways, from data-driven solution of forward and inverse PDE problems to data-driven discovery of PDEs. The goal of this project is to enable data-driven simulations in Gridap.jl supported by the 100% pure-Julia machine learning library [Flux.jl](https://github.com/FluxML/Flux.jl). This work will result in the release of the GridapFlux.jl package. The main role of the GSoC student in this project will be to develop the new GridapFlux.jl package, document it and, finally, release it in the official [Julia package registry](https://github.com/JuliaRegistries/General).

| **Intensity** | **Priority** | **Goal**  | **Mentors**  |
| -------------                          | ------------              | ------------- | -----------              |
| Moderate  |  Medium  | Enable Gridap.jl data-driven applications via Flux.jl |  [Santiago Badia](https://github.com/santiagobadia) and [Eric Neiva](https://github.com/ericneiva) |

#### Helpful Experience

- Basic knowledge of Julia
- Prior work with Gridap.jl
- Prior work with Flux.jl (not mandatory)

