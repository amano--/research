---
name: extract-frames-with-greenscreen
description: 指定された動画からフレームを抽出し、グリーンバックを透過処理します。
parameters:
  videoPath:
    type: string
    description: 処理する動画ファイルのパス。
  outputPath:
    type: string
    description: 抽出されたフレームを保存するディレクトリのパス。
---

{{
  run_in_terminal(
    command="mkdir -p \"{{outputPath}}\" && ffmpeg -i \"{{videoPath}}\" -vf \"fps=24\" \"{{outputPath}}/frame\_%03d.png\" && cd /Users/me/dev/now/movies && source .venv_for_green_screen/bin/activate && python3 process_green_screen.py",
explanation="動画からフレームを抽出し、グリーンバック透過処理を適用します。",
goal="動画フレームの抽出とグリーンバック透過処理",
isBackground=False,
timeout=0
)
}}
