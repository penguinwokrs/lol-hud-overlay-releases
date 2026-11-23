# LoL HUD Overlay 利用条件

[English](#english)

LoL HUD Overlay（以下「本ソフト」）をダウンロード・インストール・使用した時点で、この条件に同意したものとします。

## 1. 使ってよいこと
- 個人・団体を問わず、無料で使えます
- 本ソフトの画面を映した配信・動画・大会（参加費・賞金・有料配信のある大会を含む）を行い、そこから収益を得ることができます
- 本ソフトは League of Legends の観戦（リプレイを含む）専用です。自分がプレイ中の試合では何も表示しません

## 2. クレジット表記
参加費・賞金・有料配信・スポンサーなどで収益のある大会・配信で本ソフトを使う場合は、配信の概要欄・大会のページ・エンドクレジットのいずれかに、次の表記を入れてください。配信・動画・大会のページのどれも無い大会（参加者だけで行う大会など）では、表記を省略していただいてかまいません。収益のない場合も、入れていただけると開発の励みになります。

    LoL HUD Overlay — https://github.com/penguinwokrs/lol-hud-overlay-releases

HUD だけ・ドラフト（BAN/PICK の画面）だけ・両方のどれで使う場合も、この 1 行です。今までにお伝えした表記（「HUD: LoL HUD Overlay — …」や、Draft Stage の「Draft: Draft Stage — …」を含む）も、そのまま使っていただいてかまいません。

使っていただいた大会・配信を、[Issues](https://github.com/penguinwokrs/lol-hud-overlay-releases/issues/new?template=4-usage.yml) か、作者の X（[@koma_1o1](https://x.com/koma_1o1)）への DM で教えていただけると助かります（任意）。どちらか送りやすい方でかまいません。大会名・日程・配信や大会ページの URL があると嬉しいです。

## 3. 禁止すること
- 本ソフト（インストーラ・exe・同梱データ）を、配布ページ（https://github.com/penguinwokrs/lol-hud-overlay-releases）以外で再配布すること
- 本ソフトを改変すること、リバースエンジニアリングすること、改変したものを配布すること
- 本ソフトそのものに対価を求めること（販売、有料でのダウンロード・インストール・設定の代行、有料の商品やサービスへの同梱を含む）
- 本ソフトを、Riot Games の規約・ポリシーに反する目的で使うこと

## 4. 利用者の責任
- 本ソフトを使った配信・大会では、Riot Games の利用規約や大会のガイドライン（LoL Esports Community Competition Guidelines など）を利用者自身が守ってください。作者は、利用者の配信・大会が Riot Games のルールに合っていることを保証しません
- 本ソフトや作者が Riot Games の公認を受けているかのように示さないでください

## 5. 本ソフトがすること（データの扱い）
- **読むもの**: ゲーム本体の Live Client Data API と Replay API（どちらも PC 内の `127.0.0.1:2999`。Replay API からは表示の設定（`/replay/render`）だけを読みます）、LoL クライアントの LCU（PC 内のローカルの API）、観戦画面の表示。HUD が LCU から読むのは、ゲームのデータ（`/lol-game-data/assets/` の下にあるアイテム・価格・チャンピオン・スキン・スペルのデータと画像）だけです。ドラフト（BAN/PICK の画面）の機能がオンのときは、LCU からチャンピオン選択の状態（`/lol-champ-select/v1/session`）・ロビー（`/lol-lobby/v2/lobby`）・試合の進行（`/lol-gameflow/v1/session`・`/lol-gameflow/v1/gameflow-phase`）・クライアントの版（`/system/v1/builds`）も読みます。チャットの鍵・ロビーのパスワード・観戦の鍵などは、読んだらすぐに捨て、どこにも渡しません。LCU の接続先とパスワードはクライアントの `lockfile` から読み、パスワードは LCU への接続にだけ使います（保存・外部への送信はしません）。画面の文字・数字の読み取りは PC 内で行い、画像を外部へ送ることはありません
- **書き換えるもの**: ゲームの設定ファイル `PersistedSettings.json` のうち、観戦用の項目だけを書き換えます。通常プレイの設定は変えません。書き換える前のファイルは `%LOCALAPPDATA%\com.penguinwokrs.lolhudoverlay\settings-backup\` に残します。また、Stream Deck などからゲームの観戦 HUD を切り替える操作をしたときだけ、Replay API（`/replay/render`）でゲームの観戦 HUD を簡易表示（A キーを 1 回押したときと同じ。スコア・スコアボード・選手の枠・タイムライン・キルの通知・選んでいる対象・リプレイの操作の表示を消す）にし、もう一度操作すると元に戻します
- **保存するもの**: 設定・画像とゲームのデータ（JSON）のキャッシュ・試合の記録を `%LOCALAPPDATA%\com.penguinwokrs.lolhudoverlay\` に保存します
- **通信先**: 更新と表示用データの確認（GitHub）、ゲームの画像・データの取得（Riot Games の Data Dragon。Data Dragon に無い一部の画像と、ドラフトのチャンピオンのデータ・LoL クライアントから取れない画像は CommunityDragon）だけです。利用状況の収集・送信はしません。利用者自身のアカウント情報は扱いません。観戦中の試合の選手の Riot ID は、Live Client Data API から読んで HUD に表示し、試合を見分けるために PC 内（`%LOCALAPPDATA%\com.penguinwokrs.lolhudoverlay\games.json`、最大 3 試合分）に保存しますが、外部へは送りません。ドラフトは、チャンピオン選択に参加している選手の Riot ID（`gameName`・`tagLine`）と `puuid` を LCU から読み、画面への名前の表示とロールの対応付けに使います。これらはメモリに持つだけでファイルには保存せず（設定画面で入力した表示名の対応表と、使ったチャンピオンの記録は保存します）、PC の外へは送りません（同じ PC の `127.0.0.1` で開くページ（OBS のブラウザソースなど）にだけ渡します）

## 6. 保証しないこと
- 本ソフトはアルファ版で、現状のまま提供します。表示の正確さ、動作、ゲームの今後のパッチへの対応は保証しません
- 本ソフトを使ったこと、または使えなかったことで生じた損害（配信・大会の進行への影響、データの消失を含みます）について、作者は責任を負いません
- 機能の変更や配布の終了を、予告なく行うことがあります

## 7. 権利
- 本ソフトの著作権は作者（penguinwokrs）にあります
- 本ソフトが使っているオープンソースソフトウェアのライセンスは、アプリの設定画面の「アプリ情報」→「オープンソースのライセンス」で確認できます。同じ内容のファイル（THIRD-PARTY-NOTICES.html）を、インストーラと [各リリース](https://github.com/penguinwokrs/lol-hud-overlay-releases/releases) にも添付しています
- 表示する画像・名称などのゲームのデータは Riot Games の権利物です。本ソフトにはこれらを同梱せず、利用者の PC が取得します

## 8. Riot Games について
LoL HUD Overlay was created under Riot Games' "Legal Jibber Jabber" policy using assets owned by Riot Games. Riot Games does not endorse or sponsor this project.

本ソフトは Riot Games の公認・後援を受けたものではありません。

## 9. 条件の変更
この条件は予告なく変えることがあります。変更後に本ソフトを使った場合は、新しい条件に同意したものとします。

## 10. 問い合わせ
不具合の報告や質問は [Issues](https://github.com/penguinwokrs/lol-hud-overlay-releases/issues) へお寄せください。

最終更新: 2026-11-23

---

<a id="english"></a>
# LoL HUD Overlay Terms of Use

By downloading, installing, or using LoL HUD Overlay ("the Software"), you agree to these terms. If the Japanese and English versions differ, the Japanese version prevails.

## 1. What you may do
- Use the Software free of charge, as an individual or an organization
- Stream, record, or run tournaments with the Software on screen (including tournaments with entry fees, prize pools, or paid broadcasts), and earn revenue from them
- The Software is for spectating League of Legends (including replays) only. It shows nothing while you are playing a match yourself

## 2. Credit
If you use the Software in a tournament or broadcast that generates revenue (entry fees, prize pools, paid broadcasts, sponsorships, etc.), please include the following credit in the stream description, the tournament page, or the end credits. If your tournament has no broadcast, video, or tournament page (for example, one held among participants only), you're welcome to leave the credit out. For non-revenue use, a credit is appreciated but not required.

    LoL HUD Overlay — https://github.com/penguinwokrs/lol-hud-overlay-releases

Use this one line whether you use only the HUD, only the draft (ban/pick screen), or both. Credits we gave you earlier (including "HUD: LoL HUD Overlay — …" and Draft Stage's "Draft: Draft Stage — …") remain valid as they are.

We'd love to hear where the Software was used. Let us know in [Issues](https://github.com/penguinwokrs/lol-hud-overlay-releases/issues/new?template=4-usage.yml) or by DM to the author on X ([@koma_1o1](https://x.com/koma_1o1)), whichever you prefer (optional). The tournament name, date, and broadcast or tournament page URL are helpful.

## 3. What you may not do
- Redistribute the Software (installer, executable, or bundled data) anywhere other than the official download page (https://github.com/penguinwokrs/lol-hud-overlay-releases)
- Modify, reverse engineer, or distribute modified versions of the Software
- Charge for the Software itself, including selling it, charging to download, install, or set it up, or bundling it with a paid product or service
- Use the Software for any purpose that violates Riot Games' terms or policies

## 4. Your responsibilities
- When you stream or run a tournament with the Software, you are responsible for following Riot Games' Terms of Service and competition guidelines (such as the LoL Esports Community Competition Guidelines). The author does not guarantee that your broadcast or tournament complies with Riot Games' rules
- Do not present the Software, or its author, as endorsed by Riot Games

## 5. What the Software does with data
- **Reads**: the game's Live Client Data API and Replay API (both `127.0.0.1:2999` on your PC; from the Replay API, it reads only the render settings (`/replay/render`)), the League client's LCU (a local API on your PC), and the spectator screen. For the HUD, it reads only game data from the LCU (item, price, champion, skin, and spell data and images under `/lol-game-data/assets/`). When the draft (ban/pick screen) feature is on, it also reads champion select (`/lol-champ-select/v1/session`), the lobby (`/lol-lobby/v2/lobby`), game flow (`/lol-gameflow/v1/session`, `/lol-gameflow/v1/gameflow-phase`), and the client version (`/system/v1/builds`) from the LCU. Chat tokens, lobby passwords, spectator keys and similar values are dropped as soon as they are read and are not passed on. It finds the LCU's address and password in the client's `lockfile`, and uses the password only to connect to the LCU (it is not stored or sent anywhere else). Text and numbers are read on your PC, and no images are sent anywhere
- **Modifies**: only the spectator-related entries in the game's `PersistedSettings.json`. Your normal gameplay settings are not changed. A backup of the original file is kept in `%LOCALAPPDATA%\com.penguinwokrs.lolhudoverlay\settings-backup\`. Also, only when you switch the game's spectator HUD from Stream Deck or a similar controller, the Software uses the Replay API (`/replay/render`) to put the game's spectator HUD into its compact view (the same as pressing A once: it hides the score, scoreboard, player frames, timeline, kill callouts, selected target, and replay controls), and restores it when you switch again
- **Stores**: settings, a cache of images and game data (JSON), and match records in `%LOCALAPPDATA%\com.penguinwokrs.lolhudoverlay\`
- **Connects to**: GitHub (to check for updates and display data) and Riot Games' Data Dragon (to download game images and data; CommunityDragon for a few images that Data Dragon doesn't have, and for the draft's champion data and images the League client can't provide). It does not collect or send usage data, and it does not handle your own account information. The Riot IDs of the players in the match you are spectating are read from the Live Client Data API, shown on the HUD, and stored on your PC (in `%LOCALAPPDATA%\com.penguinwokrs.lolhudoverlay\games.json`, for up to 3 matches) to tell matches apart, but they are never sent anywhere. The draft reads the Riot IDs (`gameName`, `tagLine`) and `puuid` of the players in champion select from the LCU, and uses them to show names on screen and match players to roles. They are kept in memory only and not saved to files (the display-name table you enter in the settings and the record of champions used are saved), and they are never sent off your PC (they are passed only to pages opened at `127.0.0.1` on the same PC, such as OBS browser sources)

## 6. No warranty
- The Software is alpha software, provided "as is". There is no guarantee that what it displays is accurate, that it works, or that it will keep working with future game patches
- The author is not liable for any damages resulting from the use of, or inability to use, the Software, including disruption to broadcasts or tournaments and loss of data
- Features may change, and distribution may end, without notice

## 7. Rights
- The copyright in the Software belongs to its author (penguinwokrs)
- Licenses for the open-source software used by the Software can be viewed in the app (Settings → About → Open-source licenses). The same file (THIRD-PARTY-NOTICES.html) is included in the installer and attached to [each release](https://github.com/penguinwokrs/lol-hud-overlay-releases/releases)
- Game images, names, and other game data belong to Riot Games. They are not bundled with the Software; your PC downloads them

## 8. About Riot Games
LoL HUD Overlay was created under Riot Games' "Legal Jibber Jabber" policy using assets owned by Riot Games. Riot Games does not endorse or sponsor this project.

## 9. Changes to these terms
These terms may change without notice. If you use the Software after a change, you agree to the updated terms.

## 10. Contact
Please report bugs or ask questions in [Issues](https://github.com/penguinwokrs/lol-hud-overlay-releases/issues).

Last updated: 2026-11-23
