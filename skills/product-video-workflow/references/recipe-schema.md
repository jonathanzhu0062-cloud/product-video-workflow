# recipe.json Schema

Use this reference before creating or editing `work/recipe.json`.

## Purpose

`recipe.json` is the central rough-cut structure. It describes the reference video's reusable pacing and shot pattern without requiring reuse of the original footage.

## Recommended Schema

```json
{
  "platform": "douyin",
  "aspect_ratio": "9:16",
  "resolution": "1080x1920",
  "target_duration": 36,
  "voiceover": {
    "provider": "doubao",
    "path": "work/audio/video_01.wav"
  },
  "shots": [
    {
      "id": "s01",
      "start": 0.0,
      "end": 3.0,
      "duration": 3.0,
      "type": "hook",
      "description": "Pain-point opening or attention hook",
      "keyframe": "work/keyframes/s01.jpg",
      "asset_category": "hook",
      "notes": "Keep this visually strong; first 3 seconds matter most."
    }
  ]
}
```

## Shot Types

Use these labels unless the project needs a custom taxonomy:

- `hook`: first attention-grabbing shot.
- `product`: product reveal or main product shot.
- `closeup`: texture, detail, packaging, ingredient, mechanism, or quality proof.
- `usage`: product in use.
- `feature`: function demonstration.
- `comparison`: before/after, old/new, with/without, price/value comparison.
- `lifestyle`: contextual scene or user scenario.
- `proof`: testimonial, result, review, credential, or social proof.
- `ending`: call to action, final product shot, or offer reminder.

## 36-Second Pacing Template

Default pacing:

```text
0-3s: hook
3-7s: product reveal
7-14s: sell point 1
14-21s: use case or demonstration
21-29s: sell point 2 or comparison
29-34s: proof or value summary
34-36s: light call to action
```

Adapt the template to match the reference video, but preserve the 36-second target unless the user overrides it.

## Validation Checklist

Before using a recipe:

- Total duration is close to 36 seconds.
- Each shot has `id`, `duration`, `type`, and `asset_category`.
- The first shot is a clear hook.
- Product appears early.
- Ending exists.
- Asset categories map to folders under `assets/`.
- Notes identify anything that needs human review.
