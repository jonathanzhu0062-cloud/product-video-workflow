---
name: product-video-workflow
description: Plan and run a reusable Douyin product-video rough-cut workflow from reference videos and a local asset library. Use when the user wants Codex to organize assets, analyze a product showcase or e-commerce reference video, create a 36-second 9:16 Douyin video production plan, define recipe.json shot structure, prepare batch rough-cut instructions, or list manual steps for Doubao voiceover and Jianying/CapCut polish.
---

# Product Video Workflow

## Defaults

- Platform: Douyin.
- Aspect ratio: 9:16.
- Resolution: 1080x1920.
- Target duration: 36 seconds.
- Voiceover: Doubao by default, unless the user chooses another TTS.
- Output level: batch rough cuts for human review, not final fully polished videos.

## Workflow

1. Confirm the goal only when missing: product, target audience, core selling points, reference video path, available asset folder, and whether the user wants one draft or a batch.
2. Check the local project structure. Prefer:

   ```text
   assets/
   work/
   final/
   AGENTS.md
   ```

3. If the structure is missing, create or instruct creation of the missing folders before analysis.
4. Read `references/workflow.md` when the user asks for an end-to-end SOP, asks what to do next, or needs a reusable checklist.
5. Read `references/recipe-schema.md` before creating or editing `recipe.json`.
6. Read `references/manual-steps.md` before telling the user what they must do manually.
7. For reference-video analysis, generate a plan to extract shot boundaries, keyframes, durations, and shot labels. Use FFmpeg/OpenCV where available; if dependencies are absent, report the missing dependency and provide the install command.
8. Produce or update `work/recipe.json` as the central edit recipe. Do not treat the reference video's original media as reusable footage unless the user owns it.
9. Map each recipe shot to asset categories such as `hook`, `product`, `closeup`, `usage`, `feature`, `comparison`, `lifestyle`, and `ending`.
10. Build rough-cut instructions that can be implemented by scripts, FFmpeg, Jianying/CapCut, or a later execution skill.
11. Always include a human review checkpoint before final export.

## Constraints

- Keep the workflow oriented around Douyin's vertical format and 36-second pacing unless the user overrides it.
- Distinguish structure imitation from content copying. Use the reference video for pacing and shot structure, not for unauthorized reuse.
- Be explicit about what Codex can automate versus what the user must do in Doubao, Jianying/CapCut, and publishing tools.
- If asked to generate actual video files and no implementation scripts exist in the project, first create a scoped implementation plan rather than pretending the skill has a full renderer.

## Useful Prompts

Use this prompt to begin a new project:

```text
Use $product-video-workflow to set up a Douyin 9:16 product-video workflow for this product. Target duration is 36 seconds, voiceover defaults to Doubao, and I want batch rough cuts from my local assets.
```

Use this prompt after adding a reference video:

```text
Use $product-video-workflow to analyze work/reference.mp4, create work/recipe.json, and tell me which manual checks are required before generating rough cuts.
```
