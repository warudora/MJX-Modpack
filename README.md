# MJX Modpack

**MJX Modpack** は、Minecraftコミュニティ **MJX（MTR Japan Nexus）** 向けのMOD構成を管理するリポジトリです。

鉄道・都市開発・建築・交通・経済などの活動で利用するMODを、[packwiz](https://packwiz.infra.link/) で一元管理しています。

> このリポジトリはMinecraftのMOD構成・配布設定を管理するためのものです。リポジトリ内のファイルをそのままMinecraftの `mods` フォルダーに入れても動作しません。

## 対応環境

| 項目 | 設定 |
| --- | --- |
| Minecraft | **1.20.1** |
| MODローダー | **Minecraft Forge 47.4.23** |
| Java | **Java 17** |
| MOD構成管理 | **packwiz** |

環境情報は `pack.toml` を基準としています。MODの追加・更新によって必要な環境が変更される場合があります。

## 導入・更新

MJX向けに案内されているランチャーと導入手順を利用してください。

- **初めて導入する場合：** Minecraft 1.20.1 / Forge 47.4.23 / Java 17 の環境を用意し、MJXで案内されているMODパック導入方法に従ってください。
- **導入済みの場合：** packwiz対応の自動更新構成を使用している場合は、起動時の更新案内に従ってください。自動更新を設定していない環境では、利用している配布・導入方法に従って更新してください。
- **注意：** 既存のワールド・設定・セーブデータは、MOD構成を大きく変更する前にバックアップしてください。

packwizのパック定義ファイルは以下から確認できます。

- [pack.toml](./pack.toml)
- [index.toml](./index.toml)

## 主なMOD・用途

このMODパックには、以下の用途に関係するMODが含まれます。

| 分野 | 代表的なMOD |
| --- | --- |
| 鉄道 | Minecraft Transit Railway（MTR） |
| 建築・装飾 | Japaniture、各種建築用MOD |
| 工業・設備 | Create、Create Crafts & Additions |
| 経済 | Lightman's Currency |
| 利便性・制作支援 | WorldEdit、JourneyMap など |

実際に配布されるMODとバージョンの正確な一覧は、`index.toml` と `mods/` 以下の定義を参照してください。

## リポジトリ構成

```text
MJX-Modpack/
├── pack.toml      # パック名・Minecraft/Forgeのバージョン
├── index.toml     # 配布対象ファイルとハッシュの一覧
├── mods/          # MODの定義ファイル（.pw.toml）や配布対象JAR
└── README.md      # このドキュメント
```

## 管理者向け：MOD構成の変更

MODの追加・変更・削除は、原則としてpackwizを用いて行ってください。変更後はインデックスとハッシュを更新し、差分を確認した上でコミットしてください。

```sh
# MOD定義やファイルを変更した後、管理情報を更新
packwiz refresh

# 変更を確認
git diff -- pack.toml index.toml mods/
git status
```

- Forge 1.20.1に適合するMODとバージョンを選定してください。
- クライアント専用／サーバー専用／共通の区分（`side`）を適切に設定してください。
- 依存MOD、配布元、更新先、ハッシュ値を確認してください。
- `index.toml` または `pack.toml` のハッシュを手作業で適当な値に置き換えないでください。
- 複数のバージョンの同一MODが同時に配布されないようにしてください。
- 変更後は可能な限りクライアント・サーバー双方で動作確認してください。

変更の提案は、内容・目的・影響するMODを記載したPull Requestで受け付けます。

## 利用上の注意

- MJX Modpackに含まれる個々のMODや素材の著作権・ライセンスは、それぞれの制作者・配布元に帰属します。
- MODの再配布、改変、商用利用などは各MODのライセンスや利用規約を確認してください。
- このリポジトリにMODの一覧が掲載されていることは、個々のMODの権利がMJXに移転することを意味しません。

---

**MJX — MTR Japan Nexus**

Repository: [warudora/MJX-Modpack](https://github.com/warudora/MJX-Modpack)
