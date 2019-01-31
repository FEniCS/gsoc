# FEniCS Project

*This document is a draft and is subject to change*.

In all cases, we recommend that prospective students join our [Slack
channel](https://fenicsproject-slack-invite.herokuapp.com/) and work with us to
write their project proposals. The below are just sketches of ideas; if you
have your own idea, or need some input, we are more than happy to discuss it
with you!

## Gmsh/XDMF/DOLFIN mesh pipeline

### Abstract

Finite element methods require a discretisation of a domain into small
elements, called a mesh. Typically, users of DOLFIN use an external mesh
generation package, such as gmsh to construct meshes, before reading them into
DOLFIN. In this project, you will work to ensure that gmsh, DOLFIN, and our
preferred visualisation package, Paraview work seamlessly together. This will
be a huge usability improvement for users working with very complex geometries.

### Description

| **Intensity** | **Priority** | **Involves**  | **Mentors** |
| ------------- | -----------  | ------------- | ----------- |
| Moderate      | High         | Python, C++   | [Chris Richardson](mailto:chris@bpi.cam.ac.uk) |

### Technical Details

There are two possible paths that could be taken in this project:

1. Modify gmsh to directly support XDMF format files. DOLFIN directly supports
   reading and writing XDMF. Difficult.
2. Contribute to and improve meshio, a package for converting between different
   mesh file formats, e.g. gmsh's .msh and .xdmf. Easr.

### Open Source Development Experience

This project requires knowledge of C++ and Python.

### First steps

Install FEniCS from https://bitbucket.org/fenics-project/dolfin and try out the demos.
Install [ParaView](http://www.paraview.org) and view the output from the FEniCS demos.

## Use new higher-order support in Paraview for Lagrange elements

### Abstract

VTK/ParaView added support for arbitrary order Lagrange finite element
functions in the beginning of 2018. Unfortunately, the XDMF file format, which
is based on the VTK format, lacks this feature and its extension would
be helpful and keep the XDMF file format up to date.  Current DOLFIN has IO to
XDMF that could be adjusted to work with new XDMF arbitrary order Lagrange
elements. The contribution to the XDMF/VTK codebase would be a benefit for people
beyond FEniCS Project.

### Description

| **Intensity** | **Priority** | **Involves**  | **Mentors** |
| ------------- | ------------ | ------------- | ----------- |
| High          | Medium       | Python, C++   | [Michal Habera](mailto:michal.habera@uni.lu) |

### Technical Details

1. The contribution is needed in XDMF/VTK and DOLFIN codebase: XDMF/VTK could
   have arbitrary order Lagrange elements added. This would preferably involve
   extension of FiniteElementFunction format.
2. DOLFIN has support for both XDMF and VTK IO. These need to be revised/added.

VTK IO in DOLFIN is straightforward, and does not require external collaborators.
Touching the XDMF and VTK codebase is more difficult and will require
coordination with Kitware.

### Open Source Development Experience

This project requires knowledge of C++ and Python.

### First steps

Install FEniCS from https://bitbucket.org/fenics-project/dolfin and try out the demos.
Install [ParaView](http://www.paraview.org) and view the output from the FEniCS demos.

## Interface to KaHIP partitioner

### Abstract

One of main ingredients in DOLFIN’s native support of parallel computations is
the mesh partitioner. Users could pick from SCOTCH/ParMETIS, neither of which are 
actively maintained. The KaHIP partitioner is active and "the resulting system is
both more scalable and achieves higher quality than state-of-the-art systems
like ParMetis or PT-Scotch" (source: KaHIP user guide) .

### Description

| **Intensity** | **Priority** | **Involves**  | **Mentors** |
| ------------- | ------------ | ------------- | ----------- |
| High          | Medium       | Python, C++   | [Garth N. Wells](mailto:gnw20@cam.ac.uk) |

### Technical details

The partitioner KaHIP will be added to DOLFIN's graph wrappers and mesh partitioning.

### Open Source Development Experience

This project requires knowledge of C++ and Python.
