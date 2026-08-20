# cobot-atlas

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="assets/logo-light.svg">
    <img src="assets/logo-light.svg" width="180" alt="COBOT-ATLAS logo: a robotic arm transfers one mesh specimen between a source pad and worktable.">
  </picture>
</p>

**A large-scale 3D mesh dataset for robot simulation, manipulation research, and embodied AI.**

<p align="center">
<a href="https://doi.org/10.57967/hf/9199"><img src="https://img.shields.io/badge/Dataset_DOI-10.57967%2Fhf%2F9199-FF6F00?style=flat-square&logo=huggingface&labelColor=FFE4B5" alt="Dataset DOI" height="28"></a>&nbsp;&nbsp;
<a href="https://doi.org/10.5281/zenodo.20697491"><img src="https://zenodo.org/badge/DOI/10.5281/zenodo.20697491.svg" alt="Pipeline DOI" height="28"></a>
</p>

cobot-atlas provides 2,023 unique 3D meshes (glTF 2.0 Binary) spanning industrial components, geometric primitives, household items, YCB benchmark objects, robot hardware, and more — designed for collaborative robot simulation, VLA model training, and robotics benchmarking.

## Dataset

The full dataset is hosted on Hugging Face:

**[torusprime/cobot-atlas](https://huggingface.co/datasets/torusprime/cobot-atlas)** — 2,024 GLB files, 33.5 GB, MIT license.

| Category | Count | Examples |
|----------|------:|----------|
| Industrial | 734 | ICs, connectors, bearings, gears, motors, sensors, fasteners |
| Primitives | 228 | Cubes, spheres, cylinders, cones, tori in various colors |
| Household | 179 | Kitchen utensils, containers, bottles, furniture |
| Manipulation | 163 | Stacking blocks, peg-in-hole, Hanoi tower, shape sorters |
| Robotics | 88 | Robot arms, grippers, depth cameras, mobile bases |
| YCB Objects | 72 | Mustard bottle, spam can, cracker box, bowls, cups |
| Food | 66 | Fruits, vegetables, prepared items |
| + 24 more | 493 | Fabric, tools, toys, vehicles, lab equipment, medical, art supplies |
| **Total** | **2,024** | |

## This Repository

This repo contains the **generation pipeline** — scripts, manifests, and tools used to produce the dataset.

```
scripts/       — Mesh generation (fal.ai text-to-image → image-to-3D)
manifests/     — Item definitions with prompts (10 manifest files)
outputs/       — Generated meshes (GLB + reference PNG + metadata)
docs/          — Documentation and prompt reference
```

### Usage

```bash
pip install fal-client requests

# Generate meshes from manifests
python scripts/generate_meshes.py

# Verify outputs against manifests
python scripts/verify_and_document.py
```

## Sister Project

**[relief-atlas](https://github.com/sepehrmn/relief-atlas)** — 10,000+ meshes for disaster relief, humanitarian aid, and civil protection (Germany DRK/THW/Feuerwehr, EU Civil Protection, Ukraine recovery, global disaster response).

## Citation

If you use cobot-atlas in your research, please cite:

**Dataset:**

```bibtex
@misc{sepehr_mahmoudian_2026,
  author       = {Sepehr Mahmoudian},
  title        = {cobot-atlas (Revision 425eef2)},
  year         = 2026,
  url          = {https://huggingface.co/datasets/torusprime/cobot-atlas},
  doi          = {10.57967/hf/9199},
  publisher    = {Hugging Face}
}
```

**Generation pipeline:**

```bibtex
@software{cobot_atlas_code_2026,
  author    = {Mahmoudian, Sepehr},
  title     = {cobot-atlas: Generation Pipeline},
  year      = {2026},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.20697491},
  url       = {https://doi.org/10.5281/zenodo.20697491}
}
```

## License

MIT
