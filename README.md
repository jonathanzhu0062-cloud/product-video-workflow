# Product Video Workflow Skill

Codex skill for planning and running a reusable Douyin product-video rough-cut workflow.

Defaults:

- Platform: Douyin
- Aspect ratio: 9:16
- Resolution: 1080x1920
- Target duration: 36 seconds
- Voiceover: Doubao
- Output: batch rough cuts for human review and Jianying/CapCut polish

## Install Locally

Copy the skill folder into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R skills/product-video-workflow ~/.codex/skills/
```

Restart Codex if the skill does not appear immediately.

## Use

Example prompt:

```text
Use $product-video-workflow to set up a 36-second 9:16 Douyin product-video workflow with Doubao voiceover.
```

The skill helps Codex organize assets, analyze a reference video structure, create a `recipe.json` plan, identify manual Doubao and Jianying/CapCut steps, and prepare batch rough-cut instructions.

## Structure

```text
skills/product-video-workflow/
  SKILL.md
  agents/openai.yaml
  references/
    workflow.md
    recipe-schema.md
    manual-steps.md
```
