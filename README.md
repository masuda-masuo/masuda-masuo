# Hi there, I'm masuda-masuo 👋

**AI-Native Infrastructure Builder / Developer**

AIエージェント（LLM）が自律動作し、人間と共生してソフトウエアを構築する時代における、**「Agent Experience (AX)」**に最適化された安全で堅牢なAI専用インフラ・ツールチェインの開発を行っています。

プロンプトによる指示（賢さ）だけに頼る安全対策には限界があります。LLMの認知の弱点（コンテキスト崩壊、焦りによる自己破壊ループ、データと命令の混同）を、「**檻（隔離サンドボックス）**」と「**プロキシ（ポインタ検索）**」というインフラの境界で構造的にカバーする設計論を追求しています。

---

## 🛠️ Project Portfolio

AIエージェントの能力を安全に200%引き出すための、自作MCPサーバーおよびサンドボックス基盤のポートフォリオです。

### 1. [sunaba](https://github.com/masuda-masuo/sunaba) 🏜️
> **AIエージェント専用の強固な隔離サンドボックス ＆ 検証ゲートMCP**

*   **概要**: AIエージェントが安全にコマンドを実行し、ファイルを編集するためのDockerコンテナ隔離スペース。
*   **コアバリュー**: AIが提案するコード変更に対し、型チェック（mypy）、テスト（pytest）、静的解析（ruff）などの検証を完全にパスしない限りコード変更の提出を認めない**「検証ゲート（Strict Submit）」**をインフラ側で強制します。AIの自爆やバグ混入を物理的にブロックします。
*   **AX設計**: AIのパニックループを止める「Undoタイムマシン（`undo_file_edit`）」や、オフバイワンを許容するパッチ適用（`git apply --recount`）などを標準装備。

### 2. shiori (栞) 🔖 (Private — Coming Soon)
> **プロジェクトの「ファクト」と「意図」を繋ぐローカル3層RAG検索MCP**

*   **概要**: AIエージェントがソースコードやドキュメント（What/How）だけでなく、過去の Issue や PR の議論ログ（Why）を横断的かつ超高速に探索するためのローカル検索サーバー。
*   **コアバリュー**: ファイルを丸ごとLLMに読ませてコンテキストを破壊するのを防ぐため、最小限の座標情報のみを返す**「Pointer-then-Fetch」**モデルを採用。
*   **アーキテクチャ**: GitHub APIの中継プロキシではなく、ローカルの PostgreSQL（`pgvector` + `pgroonga`）と Shallow Clone によるローカル3層データストアを構築し、爆速かつセキュア（完全オフライン）に機能します。

### 3. [shiori-demo](https://github.com/masuda-masuo/shiori-demo) 📚
> **AIが「栞」を使って自律執筆した「AI失敗学コラム」デモギャラリーポータル**

*   **概要**: Shiori の検索能力をフルに使い、AI自身が「自律動作中に直面したインシデント（CUDAの遅延、ハング、キャッシュの罠など）」をRAG探索しながら自律的にまとめ上げた43本の技術コラムアーカイブ。
*   **実走検証**: サイトの「About Shiori」タブでは、実際の `sunaba` で起きたバグ（Issue #380/390）をもとに、AIエージェントがShioriからピンポイントで修正コードをFetchする協調プロセスをライブ体験できます。
*   **デモサイト**: [https://masuda-masuo.github.io/shiori-demo/](https://masuda-masuo.github.io/shiori-demo/)

### 4. [mcp-launcher](https://github.com/masuda-masuo/mcp-launcher) 🚀
> **MCPサーバーの安全なオーケストレーション ＆ 認証隔離プロキシ**

*   **概要**: 複数のMCPサーバーを立ち上げ、トークン供給やセキュリティ境界を自律制御するランチャシステム。GitHub Appの鍵情報を安全に隠蔽しつつ、コンテナ内のAIに必要な権限トークンを動的に供給します。

---

## 📖 Tech Writing (Zenn)

AIエージェント専用インフラ（AX設計）の開発から得られた生々しいバグと、その構造的解決策について技術記事を執筆しています。

*   [AI専用開発環境「sunaba」に学ぶ：LLMの編集ミスと焦りループを防ぐAIネイティブなツール設計](https://zenn.dev/masuo/articles/2026-07-17-sunaba-edit-tools)
*   [Claude Code時代のAIエージェント専用「サンドボックス」設計論（sunabaの進化）](https://zenn.dev/masuo/articles/2026-07-11-sunaba-evolution)
*   [AIが栞（Shiori）を使って書いた「AI失敗学」コラム43本と、実走デモサイトを公開しました](https://zenn.dev/masuo/articles/2026-07-18-shiori-demo-site-launch)（下書き公開予定）

---

## 📬 Contact & Socials

*   **GitHub**: [@masuda-masuo](https://github.com/masuda-masuo)
*   **Zenn**: [masuo](https://zenn.dev/masuo)
