# Changelog

このファイルは [Keep a Changelog](https://keepachangelog.com/ja/1.1.0/) の形式に従います。

## [0.1.1] - 2026-10-29

hub の E2E テスト（`e2e/`）で見つかった、Skill の記述と MCP の挙動の食い違いを直しました。手順の骨組みは変えていません。

### 修正

- Phase 6: 書いた DM の訳先の言語と題名は、`read_data_module` の `section: "outline"` では出ません。`section: "identAndStatus"`（または `all`）で読む、に直しました。
- 前提 MCP の reader の最低版を 0.7.1 に上げました。Phase 6 に、書いた直後の DM が見えること（0.7.1 以降）と、それより古い版では見えないことがあり、その場合は reader を起動し直すことを書きました。

## [0.1.0] - 未リリース

- 初版（`skills/s1000d-translate/SKILL.md` と `references/`、`evals/trigger-eval.json`）。
