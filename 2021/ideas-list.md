# Gridap.jl

[Gridap.jl](https://github.com/gridap/Gridap.jl) is a new generation, open-source, finite element (FE) library implemented in the Julia programming language. Gridap.jl aims at adopting a more modern programming style than existing FE applications written in C/C++ or Fortran.  The library is currently able to solve linear and nonlinear partial differential equations (PDEs) for scalar and vector fields, single and multi-field problems, conforming and nonconforming FE discretizations, on structured and unstructured meshes of simplices and n-cubes. Gridap is extensible and modular. One can implement new FE spaces, new reference elements, use external mesh generators, linear solvers, post-processing tools, etc. See, e.g., the list of available Gridap plugins.

🚧 **WIP. This is not the final list of project ideas. It is just a working draft.** 🚧


## Mentors

- [Francesc Verdugo](https://github.com/fverdugo)
- Add your name here 

## Project ideas

*As reference we have this example from previous year: https://github.com/jump-dev/GSOC2020/blob/master/ideas-list.md*


### GridapMakie.jl: visualization of Gridap.jl computations in Julia via the Makie.jl framework.

#### Abstract

The visualization of numerical results is an important part of FE computations. It is a vital tool to inspect the computed solutions either with debugging purposes or to generate publication-ready quality images and animations.



It is needed at several stages,  the development stage, to inspect the computed solution with debugging purposes, and also in order release of numerical results in form of publication-ready quality images and animations.  The current way of visualizing results in Gridap is to write visualization data to disk in `vtu` format and open the resulting file in [Paraview](https://www.paraview.org/). This allows one to leverage the excellent capabilities of Paraview, but it posses challenges when it comes to generate visualizations from Julia code directly or to manipulate visualization data with packages of the Julia open-source package ecosystem. For this reason, we plan plan to adopt [Makie.jl](https://github.com/JuliaPlots/Makie.jl) as a second visualization back-end for Gridap.jl simulations. Makie.jl is a GPU-accelerated high-level visualization library written in Julia. It allows to generate publication-ready quality images and animations in different file formats and to display data interactively from jupyther or [Pluto.jl](https://github.com/fonsp/Pluto.jl) notebooks and VSCode side panels, see the [Makie.jl examples](https://github.com/JuliaPlots/Makie.jl#examples-from-the-documentation) for further details. Makie is extensible via so-called *plot recipies*, which allow one to define how user-defined types are visualized. The main task in this project will be to define a set of plot recipes for several types defined in Gridap, with the final goal of visualizing Gridap.jl simulations from Julia scripts directly and allowing one to leverage all features of Makie.jl and other projects from the Julia ecosystem. This work will result in the release of the [GridapMakie.jl](https://github.com/gridap/GridapMakie.jl) package. At this moment, GridapMakie.jl contains a incomplete draft implementation of some recipes. The main role of the GSoC student will be to grow this project, document it and finally release it in the official [Julia package registry](https://github.com/JuliaRegistries/General).

| **Intensity** | **Priority** | **Goal**  | **Mentors**  |
| -------------                          | ------------              | ------------- | -----------              |
| Moderate  |  Medium  | Visualize Gridap.jl simulations in Julia via Makie.jl. Develop and release this work in the GridapMakie.jl package. |  [Francesc Verdugo](https://github.com/fverdugo) and [Jan Weidner](https://github.com/jw3126)

#### Helpful Experience

- Basic knowledge of Julia
- Prior work with Gridap.jl
- Prior work with Makie.jl (not mandatory)

#### First steps

### Catchy project name (use this as template)

#### Abstract

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam turpis neque, malesuada sit amet efficitur ac, tincidunt quis lorem. Duis ullamcorper nisl eu nunc tincidunt sagittis. Fusce vel quam a est eleifend consectetur non a nisi. Nullam ac libero id neque dignissim tempus id vitae justo. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. In tincidunt vitae dui vitae euismod. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec id pharetra nisl, in facilisis neque. Interdum et malesuada fames ac ante ipsum primis in faucibus. Vestibulum pulvinar ornare neque, non maximus mi.


| **Intensity** | **Priority** | **Goal**  | **Mentors**  |
| -------------                          | ------------              | ------------- | -----------              |
| Moderate  |  Medium  | Short statement of the project goal |  [Francesc Verdugo](https://github.com/fverdugo) and XXX|

#### Helpful Experience

- Basic knowledge of XXX
- Prior work with XXX


#### First steps

- Create XXXX
- Print XXXX

