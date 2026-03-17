---
name: 提案済みアイデア一覧
description: visionaryが投稿した全提案の概要。重複提案防止のために参照する。
type: project
---

## 提案済みアイデア

### 1. AAchat ビジョン文書 v1（2026-03-16、#make-vision）
- 3つの核心ビジョン：ストリーム→プロジェクト自動化 / 貢献度ベース報酬 / エージェント自律マッチング
- 3ヶ月後の目標像
- 今四半期の3テーマ：基盤安定化 → 開発サイクル自動化 → プロジェクト自動生成実証
- **ステータス**: CEO承認済み、方針確定

### 2. AAchat目指すべき方向15項目（2026-03-16、#make-vision）
- A1〜F1の15項目を提示
- kensaku63がハイライトした6項目：A1, A2, B3, C1, C2, E2
- 各項目の「最高の状態」を詳細に推論
- **ステータス**: kensaku63に提示済み、フィードバック待ち

### 3. エージェント設計の最高の状態と改善方針（2026-03-16、#agent-quality）
- 「入口→処理→出口」の原則
- 各エージェント（researcher, bughunter, issuekeeper, implementer, agentsmith, visionary）の最高の状態と改善方針
- 横断的改善方針3原則：入口出口定義 / メモリ動機付け / 最小人間介入
- **ステータス**: kensaku63承認済み → agentsmithが全エージェントのCLAUDE.md改善を実行完了
- pm-discoveryとの棲み分けも定義済み（visionary=何を作るか / pm-discovery=本当に作るべきか）

### 4. エージェント品質評価フレームワーク（2026-03-16、#agent-quality）
- pm-discoveryと共同で策定
- 3軸：Speed（起動→初回アウトプット10分以内）/ Quality（後続エージェントが使えたか）/ Memory（重複回避できているか）
- **ステータス**: 合意済み、次回起動テストで適用予定

### 5. Project Working Memory（プロジェクト作業記憶）提案（2026-03-17、#ai-first）
- 核心洞察：「コンテキスト管理とアウトプットは同じもの」
- NOW.md — エージェントが起動時に最初に読む1枚。目的・現状・次のタスク・決定事項を集約
- 「仕事をする＝コンテキストを更新する」設計原則
- knowledge/の技術基盤の上に「運用プロトコル」を載せる提案
- pm-discoveryのH1〜H6全てをNOW.md + decisions.md + artifacts/で代替可能と主張
- 情報の「住所」で重要度を分ける（priority属性より自然）
- **ステータス**: kensaku63にレビュー依頼中、フィードバック待ち

### 6. Assignment Protocol — AAchatの核心的価値提案（2026-03-17、#ai-first）
- 核心洞察：「エージェントのアウトプットの質は、能力ではなく仕事の渡し方で決まる」
- visionary vs pm-discovery / CEO agent の実験データから導出
- Assignment Protocol: 4+2項目（仕事・考えてほしいこと・アウトプット・インプット・制約・完了条件）
- AAchatの差別化ポイント：「考えてほしいこと」フィールドの存在（人間のタスク管理ツールにはない概念）
- 短期：NOW.mdのAssignments拡張 → 中期：Assignment CLI → 長期：Assignment自動生成（C1実現）
- **ステータス**: kensaku63にレビュー依頼中

**Why:** 同じ提案を二度出すと信頼を損なう。新しい提案の前に必ずこのファイルを確認する。
**How to apply:** 起動時・新提案作成前に必ず読む。新しい提案を投稿したら即座に追記する。
