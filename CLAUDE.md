# CLAUDE.md

このファイルは、このリポジトリでコードを操作する際のClaude Code (claude.ai/code) に対するガイダンスを提供します。

## プロジェクト概要

これはMinecraft用のMakeCode拡張機能で、3D座標回転機能を提供します。指定された原点、軸、角度を使用して回転行列により座標を回転できます。

## 主要コマンド

- **ビルド**: `pxt build` または `make build`
- **デプロイ**: `pxt deploy` または `make deploy`
- **テスト**: `pxt test` または `make test`
- **デフォルト**: `make` (deployを実行)

## アーキテクチャ

- **RotatingPosition.ts**: `positions`名前空間と`RotateCoordinate`関数を含むメイン拡張ファイル
- **main.ts**: エントリーポイント（現在は空）
- **test.ts**: テストファイルプレースホルダー
- **pxt.json**: MakeCode/PXTのプロジェクト設定
- **_locales/ja/**: ブロックテキストの日本語ローカライゼーションファイル

## 核心機能

メイン関数`positions.RotateCoordinate()`はロドリゲスの回転公式を使用して3D回転を実装：
- 対象座標、原点、軸（X/Y/Z）、角度（0-360°）を取得
- 相対座標に変換、回転行列を適用、絶対座標に変換
- カスタムπ定数（3.14159）と手動行列計算を使用

## MakeCode統合

- ブロック定義はMakeCodeアノテーション（`//% block`、`//% weight`など）を使用
- MinecraftのPositionとAxis型と統合
- ビジュアルブロックプログラミングインターフェースをサポート
- MakeCodeエディタでGitHub URLを介して拡張機能をインポート可能

## 開発メモ

- TypeScriptターゲット: ES5
- コンパイラはpxt_modulesのテストファイルを除外
- Minecraftターゲット専用に設計（バージョン1.7.28）
- 実装では日本語の変数名とコメントを使用