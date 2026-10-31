# 活俠傳 Gamepad Icons

Steam版『活俠傳 / Legend of Mortal』のコントローラー表示をPlayStation系アイコンへ置き換える非公式BepInEx MODです。現在の配布版は **1.0.0** です。

## 機能

- Steam Inputを有効にしたまま、ゲーム内の表示をPlayStation系へ固定します。
- Normal（白色・塗りつぶし、初期値）、Color、ColorOutline、Outlineの4スタイルを同梱しています。
- 対応する画像がない入力はゲーム内蔵のPlayStationアイコンを使用します。
- `icon-map.txt`で入力パスと画像を対応付けられます。

## ダウンロード・導入

[最新リリース](../../releases/latest)のAssetsから`LegendOfMortalGamepadIcons.zip`をダウンロードしてください。  
`Source code (zip)`はこの公開リポジトリの文書をまとめたもので、MOD本体は含みません。

1. ゲームを終了し、配布ZIPを展開します。
2. `LegendOfMortalGamepadIcons`フォルダーをゲームの`BepInEx/plugins/`へコピーします。
3. フォルダー内にDLL、`icon-map.txt`、`Icons/`があることを確認してゲームを起動します。

ZIP直下の`README_JP.txt`、`LICENSE.txt`、`THIRD_PARTY_LICENSE_KENNEY.txt`も保管してください。
旧`LegendOfMortalDualSenseIcons`がある場合は、重複読み込みを避けるため削除してください。

## 対象環境

- Steam版『活俠傳 / Legend of Mortal』、Windows 11
- Unity 2020.3.49f1 / 32-bit Mono
- BepInEx 6.0.0-be.692（別途導入が必要）

ゲーム更新後の互換性は別途確認が必要です。

## 設定

初回起動後、ゲームを終了して`BepInEx/config/lom.jp.gamepadicons.cfg`を編集してください。変更後は再起動します。

| セクション | 設定 | 初期値 | 内容 |
|---|---|---|---|
| General | Enabled | true | MOD全体を有効化 |
| General | UseCustomIcons | true | 同梱PNGを使用 |
| General | ForcePlayStationFallback | true | PNGがない入力も内蔵PS表示へ固定 |
| Debug | LogMissingIcons | true | 未登録入力と推奨画像名をログへ記録 |
| Images | IconStyle | Normal | Normal / Color / ColorOutline / Outline |
| Images | PixelsPerUnit | 100 | 画像からSpriteを作る際の倍率基準。通常は変更不要 |

## 画像の変更

`Icons/各スタイル/`の同名PNGを差し替えられます。同梱画像は128×128pxの透過PNGです。  
画像は1枚4MiB以下、最大1024×1024px、1スタイル256枚まで、全体のデコード画素数にも上限があります。`icon-map.txt`は64KiB・512行までです。

特殊な入力を割り当てる例：`<Gamepad>/buttonSouth=Cross.png`。

## 制約・削除

物理コントローラーを自動判定する機能ではなく、表示をPlayStation系へ固定します。  
Bluetooth接続などの入力自体の対応範囲は、ゲーム・Steam Inputの設定に依存します。

削除する場合は、ゲームを終了して`BepInEx/plugins/LegendOfMortalGamepadIcons`を削除してください。  
ゲーム本体のDLL・アセット・セーブデータは書き換えません。

## ライセンス

MOD本体は[MIT License](LICENSE)です。配布ZIPにも同じ本文を`LICENSE.txt`として同梱します。

同梱アイコンはKenneyの「Input Prompts (1.5A)」をファイル名変換して使用しています。  
画像にはMOD本体のMITではなくCC0が適用されます。  
[素材のライセンス・出典](THIRD_PARTY_LICENSE_KENNEY.txt)と、同文書内のCC0本文へのリンクを参照してください。この文書は配布ZIPにも同梱します。

BepInEx、HarmonyX、Unity、ゲーム本体のDLLは同梱していません。  
PlayStationおよびDualSenseは各権利者の商標です。  
本MODはSony Interactive Entertainment、ゲームの開発元・販売元が承認・提供したものではありません。
