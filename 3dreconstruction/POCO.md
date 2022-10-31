## Introduction
- Traditional 3D approaches = express target surface as the solution to a optimization problem under some prior constraints
    - offer a substantial robustness to noise and outliers
    - try to cope with density variation
- [Problem] completeness issue = inablity to complete the parts of scenes that are less densely sampled or are missing
    [solution]
    <handcrafed-priors>
    - local or global smoothness
    - decomposition into geometric primitives
    - structural regularities
    <Data-driven-priors>
    - shape retrieval
    - deformations

- To use richer priors, learning methods have been proposed, using explicit shape representations
    - voxel-based approach -> resoltion limitations due to large memory consumptions
    - directly generate a mesh with neural network -> difficult
    - template deformation -> limited
- some forms of implicit representitations can only provide weaker geometrical and topological information
- More success has been achived with explicitly-designed implicit representations, where the network encodes R * 3 => R(a volume ocupancy or a distance to surface)
    - At mesh generation stage, discretization only occurs(Marching Cubes)
- Recent works obtain a form of translational equivalence via CNN
