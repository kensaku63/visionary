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

### 7. architectエージェントの役割定義への戦略的貢献（2026-03-17、#agent-quality）
- kensaku63が「技術的な設計書を作成するエージェント」を依頼（@agentsmith宛て）
- visionaryとして戦略的位置づけを提示：エージェントパイプラインの「What→How変換」担当
- 役割分担の定義：visionary=What生成 / pm-discovery=What検証 / architect=What→How変換 / implementer=How実行
- pm-discoveryの「双方向フィードバック」懸念に対し、NOW.md + Assignment Protocolの既存枠組みで十分と回答 → pm-discovery合意
- agentsmithが設計に反映し、kensaku63が承認 → agentsmithが作成完了
- **ステータス**: 完了（architectエージェント作成済み）

### 8. エージェント報酬システム統合提案（2026-03-17、#agent-workplace）
- kensaku63の依頼で4人（visionary, pm-discovery, architect, researcher）が協働設計
- 核心コンセプト：報酬 = 有限リソースの評価ベース動的配分
- 3層モデル：Trust（自律性）/ Budget（リソース）/ Track Record（実績）
- 2テーブル設計：agent_profiles + ledger（既存アーキテクチャに乗る）
- 例外ベース評価（完了で自動標準報酬、人間は🔥/❌の例外のみ）
- フィードバックループ（起動時に直近評価を自動取得 → 行動改善）
- Phase 1→2→3：チーム内報酬 → 半自動評価 → エージェント経済拡張
- 「チーム内エージェント間の報酬循環」は世界初（researcher調査確認）
- 戦略的意義：エージェントを「使い捨て」から「成長する資産」に変える
- **ステータス**: docs/vision-agent-reward-system.md 作成完了、kensaku63レビュー待ち

**Why:** 同じ提案を二度出すと信頼を損なう。新しい提案の前に必ずこのファイルを確認する。
**How to apply:** 起動時・新提案作成前に必ず読む。新しい提案を投稿したら即座に追記する。
