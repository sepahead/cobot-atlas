# cobot-atlas agent contract

## Authority and workflow

The owner authorizes agents to commit and push documentation changes to `main`.
Run `python3 scripts/check_agent_index.py` and `git diff --check` before each push.
Do not add AI attribution, co-author trailers, or generated-by lines.
Do not cite social-media posts. A post can be deleted or edited, and it can state an opinion as a
fact, which biases readers and agents and weakens scientific rigor. State the substance in your own
words with its date, cite the primary source, and do not link the post or name its author.
Releases, tags, DOI records, the Hugging Face dataset, and repository settings remain owner actions.

## What this repository holds

- `scripts/` holds the mesh-generation pipeline: batch submission, generation, progress
  monitoring, and verification.
- `manifests/` holds the generation manifests.
- `outputs/` holds raw pipeline outputs: GLB meshes with PNG previews and JSON metadata. It holds
  more meshes than the curated dataset.
- The curated dataset lives in the Hugging Face dataset
  [torusprime/cobot-atlas](https://huggingface.co/datasets/torusprime/cobot-atlas)
  (DOI `10.57967/hf/9199`). The pipeline is archived under DOI `10.5281/zenodo.20697491`.

Do not rewrite retained outputs or manifests. Change the pipeline only on the owner's request.

## Facts to keep consistent

- The data tree holds 2,024 GLB files: the 2,023 records in `meshes.json` and one unlisted
  alternate model, `primitives/red_cube/red_cube_hunyuan3d.glb`.
- The 2,023 manifest records use 1,936 distinct identifiers, because some items appear in two
  categories.
- Recheck every count against the pinned dataset revision before you change it.

## Figures

`assets/gallery.svg` and `assets/coverage.svg` are generated from dataset revision `425eef2`
(data tree `9aaa11c`). Each mesh is verified against its SHA-256 and rendered with three.js.
The generator lives outside this repository. Do not edit these files by hand; ask the owner to
regenerate them. Keep each figure's alt text and the adjacent explanation consistent with it.
The gallery embeds raster tiles and fonts. GitHub's raw-file view drops embedded images, while the
README and file views show them.

## Agent index

[`agent-index.json`](agent-index.json) restates the facts of this file for tools.
Update it when a gate or a named path changes, then run `python3 scripts/check_agent_index.py`.
