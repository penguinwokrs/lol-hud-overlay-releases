# LoL HUD Overlay 利用条件

[English](#english)

LoL HUD Overlay（以下「本ソフト」）をダウンロード・インストール・使用した時点で、この条件に同意したものとします。

## 1. 使ってよいこと
- 個人・団体を問わず、無料で使えます
- 本ソフトの画面を映した配信・動画・大会（参加費・賞金・有料配信のある大会を含む）を行い、そこから収益を得ることができます
- 本ソフトは League of Legends の観戦（リプレイを含む）専用です。自分がプレイ中の試合では何も表示しません

## 2. クレジット表記
参加費・賞金・有料配信・スポンサーなどで収益のある大会・配信で本ソフトを使う場合は、配信の概要欄・大会のページ・エンドクレジットのいずれかに、次の表記を入れてください。収益のない場合も、入れていただけると開発の励みになります。

    HUD: LoL HUD Overlay — https://github.com/penguinwokrs/lol-hud-overlay-releases

使っていただいた大会・配信を [Issues](https://github.com/penguinwokrs/lol-hud-overlay-releases/issues/new?template=4-usage.yml) で教えていただけると助かります（任意）。

## 3. 禁止すること
- 本ソフト（インストーラ・exe・同梱データ）を、配布ページ（https://github.com/penguinwokrs/lol-hud-overlay-releases）以外で再配布すること
- 本ソフトを改変すること、リバースエンジニアリングすること、改変したものを配布すること
- 本ソフトそのものに対価を求めること（販売、有料でのダウンロード・インストール・設定の代行、有料の商品やサービスへの同梱を含む）
- 本ソフトを、Riot Games の規約・ポリシーに反する目的で使うこと

## 4. 利用者の責任
- 本ソフトを使った配信・大会では、Riot Games の利用規約や大会のガイドライン（LoL Esports Community Competition Guidelines など）を利用者自身が守ってください。作者は、利用者の配信・大会が Riot Games のルールに合っていることを保証しません
- 本ソフトや作者が Riot Games の公認を受けているかのように示さないでください

## 5. 本ソフトがすること（データの扱い）
- **読むもの**: ゲーム本体の Live Client Data API（PC 内の `127.0.0.1:2999`）と観戦画面の表示。画面の文字・数字の読み取りは PC 内で行い、画像を外部へ送ることはありません
- **書き換えるもの**: ゲームの設定ファイル `PersistedSettings.json` のうち、観戦用の項目だけを書き換えます。通常プレイの設定は変えません。書き換える前のファイルは `%LOCALAPPDATA%\com.penguinwokrs.lolhudoverlay\settings-backup\` に残します
- **保存するもの**: 設定・画像のキャッシュ・試合の記録を `%LOCALAPPDATA%\com.penguinwokrs.lolhudoverlay\` に保存します
- **通信先**: 更新と表示用データの確認（GitHub）、ゲームの画像・データの取得（CommunityDragon）だけです。利用状況の収集・送信はしません。アカウント情報も扱いません

## 6. 保証しないこと
- 本ソフトはアルファ版で、現状のまま提供します。表示の正確さ、動作、ゲームの今後のパッチへの対応は保証しません
- 本ソフトを使ったこと、または使えなかったことで生じた損害（配信・大会の進行への影響、データの消失を含みます）について、作者は責任を負いません
- 機能の変更や配布の終了を、予告なく行うことがあります

## 7. 権利
- 本ソフトの著作権は作者（penguinwokrs）にあります
- 表示する画像・名称などのゲームのデータは Riot Games の権利物です。本ソフトにはこれらを同梱せず、利用者の PC が取得します

## 8. Riot Games について
LoL HUD Overlay was created under Riot Games' "Legal Jibber Jabber" policy using assets owned by Riot Games. Riot Games does not endorse or sponsor this project.

本ソフトは Riot Games の公認・後援を受けたものではありません。

## 9. 条件の変更
この条件は予告なく変えることがあります。変更後に本ソフトを使った場合は、新しい条件に同意したものとします。

## 10. 問い合わせ
不具合の報告や質問は [Issues](https://github.com/penguinwokrs/lol-hud-overlay-releases/issues) へお寄せください。

最終更新: 2026-11-13

---

<a id="english"></a>
# LoL HUD Overlay Terms of Use

By downloading, installing, or using LoL HUD Overlay ("the Software"), you agree to these terms. If the Japanese and English versions differ, the Japanese version prevails.

## 1. What you may do
- Use the Software free of charge, as an individual or an organization
- Stream, record, or run tournaments with the Software on screen (including tournaments with entry fees, prize pools, or paid broadcasts), and earn revenue from them
- The Software is for spectating League of Legends (including replays) only. It shows nothing while you are playing a match yourself

## 2. Credit
If you use the Software in a tournament or broadcast that generates revenue (entry fees, prize pools, paid broadcasts, sponsorships, etc.), please include the following credit in the stream description, the tournament page, or the end credits. For non-revenue use, a credit is appreciated but not required.

    HUD: LoL HUD Overlay — https://github.com/penguinwokrs/lol-hud-overlay-releases

We'd love to hear where the Software was used. Let us know in [Issues](https://github.com/penguinwokrs/lol-hud-overlay-releases/issues/new?template=4-usage.yml) (optional).

## 3. What you may not do
- Redistribute the Software (installer, executable, or bundled data) anywhere other than the official download page (https://github.com/penguinwokrs/lol-hud-overlay-releases)
- Modify, reverse engineer, or distribute modified versions of the Software
- Charge for the Software itself, including selling it, charging to download, install, or set it up, or bundling it with a paid product or service
- Use the Software for any purpose that violates Riot Games' terms or policies

## 4. Your responsibilities
- When you stream or run a tournament with the Software, you are responsible for following Riot Games' Terms of Service and competition guidelines (such as the LoL Esports Community Competition Guidelines). The author does not guarantee that your broadcast or tournament complies with Riot Games' rules
- Do not present the Software, or its author, as endorsed by Riot Games

## 5. What the Software does with data
- **Reads**: the game's Live Client Data API (`127.0.0.1:2999` on your PC) and the spectator screen. Text and numbers are read on your PC, and no images are sent anywhere
- **Modifies**: only the spectator-related entries in the game's `PersistedSettings.json`. Your normal gameplay settings are not changed. A backup of the original file is kept in `%LOCALAPPDATA%\com.penguinwokrs.lolhudoverlay\settings-backup\`
- **Stores**: settings, an image cache, and match records in `%LOCALAPPDATA%\com.penguinwokrs.lolhudoverlay\`
- **Connects to**: GitHub (to check for updates and display data) and CommunityDragon (to download game images and data). It does not collect or send usage data, and it does not handle account information

## 6. No warranty
- The Software is alpha software, provided "as is". There is no guarantee that what it displays is accurate, that it works, or that it will keep working with future game patches
- The author is not liable for any damages resulting from the use of, or inability to use, the Software, including disruption to broadcasts or tournaments and loss of data
- Features may change, and distribution may end, without notice

## 7. Rights
- The copyright in the Software belongs to its author (penguinwokrs)
- Game images, names, and other game data belong to Riot Games. They are not bundled with the Software; your PC downloads them

## 8. About Riot Games
LoL HUD Overlay was created under Riot Games' "Legal Jibber Jabber" policy using assets owned by Riot Games. Riot Games does not endorse or sponsor this project.

## 9. Changes to these terms
These terms may change without notice. If you use the Software after a change, you agree to the updated terms.

## 10. Contact
Please report bugs or ask questions in [Issues](https://github.com/penguinwokrs/lol-hud-overlay-releases/issues).

Last updated: 2026-11-13
