
# annn_md2pdf

- author: laplaciannin102(Kosuke Asada)
- date: 2023/01/07
- latest version: 1.0.1

## Table of Contents

- [annn\_md2pdf](#annn_md2pdf)
  - [Table of Contents](#table-of-contents)
  - [概要](#概要)
  - [環境構築](#環境構築)
  - [使用方法](#使用方法)
  - [markdown記法](#markdown記法)
    - [共通](#共通)
    - [pdf\_A4](#pdf_a4)
    - [slide](#slide)
  - [補足](#補足)
    - [要修正事項](#要修正事項)

## 概要

- markdownで書いたテキストをpdfに変換します．
- 変換先のpdfは次の3種類の形式に対応しています．
  - A4
  - 16:9スライド
  - 4:3スライド

## 環境構築

- 実行前に次のソフトウェアをインストールし，pathを通しておいてください．
  - google chrome
  - pandoc
  - jpdfbookmark

- pathを通すとは，各ソフトウェアを実行するエイリアス(短縮コマンド)が設定されている状態を指します．
  - 例えばgoogle chromeは元々「C:\Program Files (x86)\Google\Chrome\Application\chrome.exe」の様なpathに置かれていますが，これをCLI上で「chrome」コマンドのみで実行できる状態です．


## 使用方法

1. markdown形式のテキストを書く．
   - 各種独特の記法があるため，詳細は後述する．
2. 変換先が「A4」ならば「md2pdf_a4_config.ini」を，「16:9スライド」または「4:3スライド」ならば「md2slide_config.ini」を編集する．
   1. 各種値を設定する．
   2. 使用する設定を「use_config」の値として設定する．
3. 「annn_md2pdf.exe」を起動する．
4. 変換したいmarkdownファイルを入力ファイルとして設定する．
5. 各項目を設定する．
   - 表紙の有無
   - ページ表記の有無
6. 「実行」を押下する．

---

## markdown記法
### 共通

- 改ページ

```markdown
---
```

### pdf_A4

- 表紙ページ情報
  - @xx:以下に該当する情報を記載するとpdf上で設定されます．

```markdown
<!--article_info
@title:
@subtitle:
@date:
@author:
article_info-->
```

- ページ毎のヘッダ
  - @xx:以下に該当する情報を記載するとpdf上で設定されます．

```markdown
<!--header
@left:
@right:
header-->
```

- ページ毎のフッタ
  - footerタグ内の複数行がpdf上のフッタに設定されます．
  - 引用や補足などで使用する想定．

```markdown
<!--footer
abcde
fghij
複数行も対応
footer-->
```

### slide

- 表紙ページ情報
  - @xx:以下に該当する情報を記載するとpdf上で設定されます．

```markdown
<!--slide_info
@title:
@subtitle:
@footer:
@date:
@author:
slide_info-->
```

- ページタイトル．

```markdown
<!--page_title
page header sample 001
page_title-->
```

- 中央寄せ
  - このコメントが記載されたページは上下左右中央寄せされます．

```markdown
<!--center-->
```

## 補足
### 要修正事項

- 4:3スライドにおいて，ページタイトルが全角14文字を超えるとページの下に隙間ができてしまう









