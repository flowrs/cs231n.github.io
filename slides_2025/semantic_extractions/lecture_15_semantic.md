# Lecture 15: 3D Vision

## 3D Representations Overview

```
    ┌─────────────────────────────────────────────────────────────────┐
    │                    3D REPRESENTATION TYPES                      │
    ├─────────────────────────────────────────────────────────────────┤
    │                                                                 │
    │   EXPLICIT:                    IMPLICIT:                        │
    │   ┌─────────────────────┐     ┌─────────────────────┐          │
    │   │ Point Cloud         │     │ Signed Distance     │          │
    │   │   • • •             │     │ Function (SDF)      │          │
    │   │  •     •            │     │                     │          │
    │   │   • • •             │     │ f(x,y,z) = distance │          │
    │   └─────────────────────┘     │ to surface          │          │
    │   ┌─────────────────────┐     └─────────────────────┘          │
    │   │ Polygon Mesh        │     ┌─────────────────────┐          │
    │   │    /\               │     │ Occupancy Field     │          │
    │   │   /  \              │     │                     │          │
    │   │  /____\             │     │ f(x,y,z) = 0 or 1   │          │
    │   │  vertices + faces   │     │ (inside or outside) │          │
    │   └─────────────────────┘     └─────────────────────┘          │
    │   ┌─────────────────────┐     ┌─────────────────────┐          │
    │   │ Voxel Grid          │     │ Neural Field        │          │
    │   │  ┌─┬─┬─┐            │     │                     │          │
    │   │  ├─┼─┼─┤ 3D grid    │     │ f_θ(x,y,z) = ...   │          │
    │   │  └─┴─┴─┘            │     │ (learned network)   │          │
    │   └─────────────────────┘     └─────────────────────┘          │
    └─────────────────────────────────────────────────────────────────┘
```

## Point Clouds

```
    POINT CLOUD: Unordered set of 3D points

    ┌─────────────────────────────────────────────────────────────────┐
    │   Point = (x, y, z)  or  (x, y, z, nx, ny, nz) with normal     │
    │                                                                 │
    │                    • • •                                        │
    │                  •       •                                      │
    │                 •    •    •                                     │
    │                  •       •                                      │
    │                    • • •                                        │
    │                                                                 │
    │   Properties:                                                   │
    │   + Simple to acquire (LiDAR, depth sensors)                   │
    │   + Easy to process                                            │
    │   - No connectivity information                                │
    │   - No surface, just samples                                   │
    │   - Needs spatial data structures for efficiency               │
    └─────────────────────────────────────────────────────────────────┘

    POINTNET: Deep learning on point clouds

    ┌─────────────────────────────────────────────────────────────────┐
    │   Challenge: Point clouds are unordered (permutation invariant)│
    │                                                                 │
    │   Points     Per-point        Symmetric         Global         │
    │   N×3        MLP              Function          Feature        │
    │    │          │                   │                            │
    │    ▼          ▼                   ▼                            │
    │   ┌───┐     ┌───┐              ┌─────┐          ┌───┐          │
    │   │p₁ │────►│MLP│──► f₁ ──────►│     │          │   │          │
    │   │p₂ │────►│MLP│──► f₂ ──────►│ MAX │─────────►│ g │          │
    │   │p₃ │────►│MLP│──► f₃ ──────►│POOL │          │   │          │
    │   │...│────►│MLP│──► ...──────►│     │          │   │          │
    │   └───┘     └───┘              └─────┘          └───┘          │
    │                                                                 │
    │   Max pooling = permutation invariant aggregation              │
    └─────────────────────────────────────────────────────────────────┘
```

## Polygon Meshes

```
    MESH: Vertices + Faces (connectivity)

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   Vertices V = {v₁, v₂, v₃, ...}    (3D positions)             │
    │   Faces F = {(i,j,k), ...}          (vertex indices)           │
    │                                                                 │
    │           v₂                                                    │
    │           /\                                                    │
    │          /  \                                                   │
    │         /    \           Face = triangle (v₁, v₂, v₃)          │
    │        /      \                                                 │
    │       /________\                                                │
    │      v₁         v₃                                              │
    │                                                                 │
    │   Properties:                                                   │
    │   + Explicit surface with connectivity                         │
    │   + Standard format for graphics (OpenGL, games)               │
    │   + Variable resolution (more triangles = more detail)         │
    │   - Hard to change topology                                    │
    │   - Requires good mesh quality (no self-intersections)         │
    └─────────────────────────────────────────────────────────────────┘
```

## Voxel Grids

```
    VOXELS: 3D extension of pixels

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   3D Grid of binary (occupied/empty) or continuous values      │
    │                                                                 │
    │       ┌───┬───┬───┬───┐                                        │
    │      /│   │   │   │   │                                        │
    │     ┌───┬───┬───┬───┐│                                        │
    │    /│ ■ │   │ ■ │   ││                                        │
    │   ┌───┬───┬───┬───┐││                                        │
    │   │   │ ■ │ ■ │   ├┼┘                                        │
    │   ├───┼───┼───┼───┤│                                         │
    │   │ ■ │ ■ │   │ ■ ├┘                                         │
    │   └───┴───┴───┴───┘                                           │
    │                                                                 │
    │   Resolution: N³ voxels                                        │
    │                                                                 │
    │   Properties:                                                   │
    │   + Easy to apply 3D convolutions                              │
    │   + Regular structure                                          │
    │   - Memory: O(N³) - 256³ = 16M voxels!                        │
    │   - Limited resolution for fine details                        │
    └─────────────────────────────────────────────────────────────────┘
```

## Implicit Representations

```
    SIGNED DISTANCE FUNCTION (SDF):

    ┌─────────────────────────────────────────────────────────────────┐
    │   f(x, y, z) = signed distance to surface                      │
    │                                                                 │
    │   f > 0: outside                                               │
    │   f = 0: on surface    ← Extract surface via Marching Cubes   │
    │   f < 0: inside                                                │
    │                                                                 │
    │          + + + + + + + +                                       │
    │          + + + + + + + +                                       │
    │          + + + 0 0 + + +                                       │
    │          + + 0 - - 0 + +                                       │
    │          + + 0 - - 0 + +                                       │
    │          + + + 0 0 + + +                                       │
    │          + + + + + + + +                                       │
    │                                                                 │
    │   Properties:                                                   │
    │   + Any resolution (continuous)                                │
    │   + Easy boolean operations (union, intersection)              │
    │   + Natural for collision detection                            │
    └─────────────────────────────────────────────────────────────────┘


    NEURAL IMPLICIT (DeepSDF, NeRF):

    ┌─────────────────────────────────────────────────────────────────┐
    │   Learn SDF or radiance field with neural network              │
    │                                                                 │
    │   (x, y, z) ──► MLP ──► SDF value or (color, density)         │
    │                                                                 │
    │   + Compact representation (just network weights)              │
    │   + Continuous, arbitrary resolution                           │
    │   - Slow to query (network forward pass)                       │
    └─────────────────────────────────────────────────────────────────┘
```

## NeRF (Neural Radiance Fields)

```
    NOVEL VIEW SYNTHESIS:

    ┌─────────────────────────────────────────────────────────────────┐
    │                           NeRF                                  │
    │                                                                 │
    │   Input: (x, y, z, θ, φ)  position + viewing direction         │
    │                                                                 │
    │   ┌─────────────────────────────────────────────────────────┐   │
    │   │              MLP (8 layers)                              │   │
    │   │                                                          │   │
    │   │   (x,y,z) ──► [MLP] ──► density σ                       │   │
    │   │                   └──► features ──┬──► (θ,φ) ──► RGB    │   │
    │   │                                   │                      │   │
    │   │                          view-dependent color            │   │
    │   └─────────────────────────────────────────────────────────┘   │
    │                                                                 │
    │   Output: (R, G, B, σ)  color + density                        │
    └─────────────────────────────────────────────────────────────────┘

    VOLUME RENDERING:

    ┌─────────────────────────────────────────────────────────────────┐
    │   Cast ray through each pixel:                                 │
    │                                                                 │
    │   Camera ─────●─────●─────●─────●─────► ray                    │
    │               │     │     │     │                              │
    │               ▼     ▼     ▼     ▼                              │
    │            sample points along ray                             │
    │               │     │     │     │                              │
    │               ▼     ▼     ▼     ▼                              │
    │            query NeRF at each point                            │
    │               │     │     │     │                              │
    │               └─────┴─────┴─────┘                              │
    │                       │                                        │
    │            alpha compositing                                   │
    │                       │                                        │
    │                       ▼                                        │
    │                 pixel color                                    │
    │                                                                 │
    │   C(r) = Σ T_i × (1 - exp(-σ_i × δ_i)) × c_i                  │
    │   where T_i = exp(-Σ_{j<i} σ_j × δ_j)  (accumulated transmittance)│
    └─────────────────────────────────────────────────────────────────┘
```

## Depth Estimation

```
    MONOCULAR DEPTH ESTIMATION:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   Single RGB Image ──► CNN ──► Depth Map                       │
    │                                                                 │
    │   ┌─────────────┐              ┌─────────────┐                 │
    │   │             │              │    near     │                 │
    │   │   RGB       │    ──►       │▓▓▓▓▓▓▓▓▓▓▓▓│   depth        │
    │   │   Image     │              │░░░░░░░░░░░░│   map          │
    │   │             │              │    far      │                 │
    │   └─────────────┘              └─────────────┘                 │
    │                                                                 │
    │   Uses encoder-decoder architecture (like U-Net)               │
    │   Learns from: stereo pairs, LiDAR, or synthetic data         │
    └─────────────────────────────────────────────────────────────────┘


    STEREO DEPTH:

    ┌─────────────────────────────────────────────────────────────────┐
    │   Two cameras with known baseline                              │
    │                                                                 │
    │   Left Image              Right Image                          │
    │   ┌─────────┐              ┌─────────┐                         │
    │   │    ●    │              │   ●     │                         │
    │   │  object │              │ object  │  ← disparity d         │
    │   └─────────┘              └─────────┘                         │
    │                                                                 │
    │   Depth Z = (f × B) / d                                        │
    │   f = focal length, B = baseline, d = disparity               │
    └─────────────────────────────────────────────────────────────────┘
```

## 3D Reconstruction Pipeline

```
    MULTI-VIEW RECONSTRUCTION:

    ┌─────────────────────────────────────────────────────────────────┐
    │                                                                 │
    │   1. FEATURE DETECTION & MATCHING                              │
    │      Images ──► SIFT/ORB ──► Matched keypoints                │
    │                                                                 │
    │   2. STRUCTURE FROM MOTION (SfM)                               │
    │      Keypoints ──► Camera poses + Sparse 3D points            │
    │                                                                 │
    │   3. MULTI-VIEW STEREO (MVS)                                   │
    │      Sparse points ──► Dense point cloud / mesh               │
    │                                                                 │
    │   OR: End-to-end learning (NeRF, 3D Gaussian Splatting)       │
    └─────────────────────────────────────────────────────────────────┘
```

## Key Takeaways

```
┌────────────────────────────────────────────────────────────────────┐
│ 1. 3D representations: explicit (point, mesh, voxel) vs implicit  │
│    (SDF, neural fields) - each suited to different tasks          │
│                                                                    │
│ 2. Point clouds: simple but unstructured; PointNet handles        │
│    permutation invariance with symmetric functions                 │
│                                                                    │
│ 3. Neural implicit functions (NeRF): compact, continuous,         │
│    enables novel view synthesis from multi-view images            │
│                                                                    │
│ 4. Volume rendering: integrate color/density along rays           │
│                                                                    │
│ 5. Depth estimation: monocular (CNN) or stereo (disparity)        │
│                                                                    │
│ 6. 3D vision is increasingly important for robotics, AR/VR,       │
│    autonomous driving, and 3D content creation                    │
└────────────────────────────────────────────────────────────────────┘
```
