# Douyin Product Video Workflow

Use this reference when the user wants the full operating procedure.

## Default Output

- Platform: Douyin.
- Ratio: 9:16.
- Resolution: 1080x1920.
- Duration: 36 seconds.
- Voiceover: Doubao.
- Result: rough-cut drafts for human review and Jianying/CapCut polish.

## Step 1: Prepare Tools

Required:

- Codex for workflow orchestration and scripts.
- FFmpeg for splitting, trimming, transcoding, extracting frames, and assembling drafts.
- Python 3.8+ for analysis scripts.
- Python packages such as `opencv-python`, `numpy`, `pillow`, `moviepy`, and `pydub`.
- Doubao for default voiceover generation.
- Jianying/CapCut for final polish, subtitles, effects, and export.

Suggested install commands on macOS:

```bash
brew install ffmpeg
python3 -m pip install opencv-python numpy pillow moviepy pydub
```

Optional:

```bash
python3 -m pip install openai-whisper
```

## Step 2: Create Project Structure

Prefer:

```text
project/
  assets/
  work/
  final/
  AGENTS.md
```

Use `assets/` for reusable source material, `work/` for reference videos and intermediate outputs, `final/` for approved exports, and `AGENTS.md` for local project rules.

## Step 3: Organize Assets

Recommended asset folders:

```text
assets/
  hook/
  product/
  closeup/
  usage/
  feature/
  comparison/
  lifestyle/
  ending/
  music/
  brand/
```

Keep filenames simple. The quality of batch output depends more on asset quality and classification than on automation.

## Step 4: Add Reference Video

Place the reference video in:

```text
work/reference.mp4
```

Use the reference to learn structure, pacing, shot duration, hook style, sell-point ordering, caption rhythm, and ending shape. Do not reuse the reference footage unless the user owns the rights.

## Step 5: Analyze The Reference

Analyze:

- Shot boundaries.
- Shot durations.
- Keyframes.
- Shot type labels.
- Caption or voiceover pacing if available.
- 36-second adaptation points if the reference is shorter or longer.

Create:

```text
work/recipe.json
work/keyframes/
```

## Step 6: Review The Recipe

Ask the user or perform a manual review for:

- Missed or incorrect shot cuts.
- Over-fragmented shots.
- Merged shots that should be separate.
- Wrong shot labels.
- Weak or missing first 3-second hook.
- Missing product reveal.
- Missing ending call to action.

## Step 7: Generate Copy

Create multiple 36-second scripts with different hooks:

- Pain-point hook.
- Review hook.
- Price comparison hook.
- Use-case hook.
- Counterintuitive hook.
- Feature demonstration hook.

Each script should include a hook, product reveal, two or more sell points, use case, and light call to action.

## Step 8: Generate Doubao Voiceover

Default to Doubao. Keep each voiceover aligned to a 36-second target. Export audio files with matching script numbers:

```text
work/audio/video_01.wav
work/audio/video_02.wav
```

If Doubao requires manual UI steps, tell the user exactly what to paste and where to save the resulting audio.

## Step 9: Match Assets

Map recipe shot labels to local folders:

```text
hook -> assets/hook/
product -> assets/product/
closeup -> assets/closeup/
usage -> assets/usage/
feature -> assets/feature/
comparison -> assets/comparison/
lifestyle -> assets/lifestyle/
ending -> assets/ending/
```

Initial matching can be folder-based and duration-based. More advanced matching can use script sell points, visual similarity, motion, scene, or color.

## Step 10: Generate Rough Cuts

For each draft:

- Normalize to 1080x1920.
- Trim or crop source assets to match shot durations.
- Assemble the sequence from `recipe.json`.
- Add Doubao voiceover if available.
- Add background music at lower volume if available and licensed.
- Add basic captions only if the project has a reliable subtitle method.
- Export to `work/draft/`.

## Step 11: Batch Variations

Batch output comes from varying:

- Copy.
- Voiceover.
- Opening asset.
- Product closeups.
- Usage scenes.
- Sell-point order.
- Background music.
- Caption style.
- Ending.

Do not describe batch rough cuts as fully ready final videos until they are reviewed.

## Step 12: Polish In Jianying/CapCut

Manual polish should check:

- Bad or repeated shots.
- Awkward pacing.
- Subtitle errors.
- Voiceover timing.
- Product information accuracy.
- Price or offer accuracy.
- Music volume.
- Effects, stickers, transitions, and cover.

## Step 13: Export Final

Save approved outputs to:

```text
final/
```

Before publishing, check copyright, platform compliance, product claims, subtitles, audio sync, and black frames.
