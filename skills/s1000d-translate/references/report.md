# Translation Report の雛形

SKILL.md の Phase 7 で使う。DM が複数のときは、冒頭に DM ごとの件数の表を置き、DM ごとに個票を続ける。

```markdown
# DM 翻訳レポート

- 対象: <DMC、版、元の言語、ファイル名>
- 訳先: <languageIsoCode-countryIsoCode>、訳した DM のファイル名（推定を含む）: <fileName>
- 使用ツール: <MCP の名前と、分かる範囲の版>

## 機密区分

- 対象 DM の値: <`securityClassification.dataModule`>、本文の要素の値: <`inContent`>
- DeepL への送信: <利用者の答え / 送っていない / 未実施（DeepL の MCP 未接続）>

## 文の件数

| 項目 | 件数 |
|---|---|
| 取り出した文（`counts.total`） | <N>（title / para / step / admonition / table / caption の内訳） |
| 訳して適用した文（`applied` から「そのまま」を除く） | <N> |
| 元の文のまま適用した文（そのまま） | <N>（`id` を列挙） |
| 差し戻せなかった文（`unapplied[]`） | <N> |
| 取り出していない文（`include` / `maxSegments` で外した分、取り出されない文） | <内容と件数または「あり」> |

## 採点

xcomet: <使用 / 未実施（ツール未接続）>。閾値: 低得点 0.7 未満、DeepL との差 0.05（出発点の値。`references/scoring.md`）

| 区分 | 件数 |
|---|---|
| 平均 | <average_score> |
| 合格 | <N> |
| 低得点 | <N> |
| critical あり | <N> |

### 低得点・critical の文

| `id` | 元の文 | 自分の訳（得点） | DeepL の訳（得点） | 採用 | 理由 |
|---|---|---|---|---|---|

### DeepL の訳に差し替えた文

| `id` | 差し替えた理由（得点差、用語、プレースホルダーの確認） |
|---|---|

## 差し戻せなかった文

| `id` | `reason` | 対応 |
|---|---|---|
| <id> | <placeholder-mismatch / unknown-id / duplicate-id> | <直して再適用した / 元の言語のまま残した> |

`skeleton-mismatch` が出たとき: <出た旨、`expected` と `actual`、Phase 1 からやり直したか>

## 用語

用語集: <ファイル名と形式 / DeepL の用語集の名前 / なし>。用語集に無く新しく訳した語: <原語と訳語の一覧>

## 検証状態

| 工程 | 状態 | 備考 |
|---|---|---|
| XSD | <valid / invalid / schema-not-found / not-run> | <schema-not-found は「未検証」> |
| BREX | <passed / violations / incomplete / not-run> | |
| 参照 | <resolved / unresolved / not-run> | <no-csdb の理由なら「CSDB のフォルダー未指定のため未実施」> |

`valid` と `passed` は、XSD と機械で検査できる BREX のルールに誤りが無かったことだけを意味する。S1000D への準拠は判定していない。

## 書き込み

<`written` のパス / `write: false` のまま（確認待ち） / `writeSkipped`: 理由>

## 未訳の箇所と未実施の項目

- 訳していない箇所: <識別・状態部のデータ制限の文など、取り出されない文。元の言語のまま>
- <「未実施（ツール未接続）」: xcomet-mcp、DeepL の MCP、reader-mcp>

## 次の操作

- <利用者が決めること（上書き、用語集への追加、低得点の文の扱い）>
```
