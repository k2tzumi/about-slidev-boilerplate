---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  Slidevの快適な執筆環境をテンプレートリポジトリとして公開しました

drawings:
  persist: false
transition: slide-left
title: Slidevのテンプレートリポジトリについて
mdc: true
addons:
  - "@katzumi/slidev-addon-qrcode"
  - "slidev-addon-components"
---

# Slidevのテンプレートリポジトリについて

Dec 3rd, 2023. @ v0.0.1

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/k2tzumi/slidev-boilerplate" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
layout: two-cols-header
---

# 自己紹介

katzumi（かつみ）と申します。  

以下のアカウントで活動しています。    

::left::

<img src="https://pbs.twimg.com/profile_images/799890486773170176/KN4gKfS2_400x400.jpg" class="rounded-full w-40 mt-16 mr-12　float-left"/>  
<QRCode width="180" height="180" value="https://twitter.com/katzchum" color="4329B9" image="Logo_of_X.svg" />

<simple-icons-x /> [katzchum](https://twitter.com/katzchum)

::right::

<img src="https://avatars.githubusercontent.com/u/1182787?v=4" class="rounded-full w-40 mt-16 mr-12"/>

<logos-github-octocat /> [k2tzumi](https://github.com/k2tzumi)  
<simple-icons-zenn /> [katzumi](https://zenn.dev/katzumi)  

<br />

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: fade-out
---

# What is Slidev？

Markdown 形式のフォーマットを書くといい感じにスライドが出来ます！  
収録機能があり、素振りにも最適。

オフィシャルページはこちら  
https://sli.dev/


![Logo](https://sli.dev/logo-title.png)

---
layout: two-cols-header
transition: fade-out
---

# いままでSlidevで作ったスライド

LT 用のちょっとしたスライドから、技術カンファレンスのスライドまで

::left::

https://www.docswell.com/user/katzumi

<QRCode width="180" height="180" value="https://www.docswell.com/user/katzumi" color="4329B9" />

::right::

<img src="/slides.png" class="h-100 rounded shadow" />

---
layout: fact
---

# いっぱい作った

書き味は大変良くスラスラ書ける


<div v-click class="text-xl">

もっと便利に使いたい！

</div>

---
layout: default
---

# Motivation

スライドを最速で量産するのに、執筆〜公開までの一連のプロセスを改善したい

- 素振り・本番・公開後それぞれのバージョンをいい感じに管理したい
- スライド共有サイト以外でスライドを自前公開をしたい
  - Google Analytics でアクセスログを見れるように
  - SNS へ共有する際に OGP でいい感じに
  - 最新バージョンが勝手
- よく使う slidev のコマンドをまとめておきたい
- typo とかはなるべくなくしたい
- 自作アドオンがデフォルトで有効にしたい
- よく使う CSS とかも管理したい
- 上記の執筆環境を環境依存せずにすぐ立ち上げたい

---
layout: center
---

# Slidev用のテンプレートリポジトリ作りました

https://github.com/k2tzumi/slidev-boilerplate

---
layout: image-right
image: https://source.unsplash.com/collection/94734566/960x1080
---

# boilerplate機能紹介
使い方にも触れます


---
layout: default
---

# tagprによるバージョン管理
素振り・本番・公開後それぞれにバージョンを付けるようにします

tagpr を GitHub Actions のワークフローに組み込んでバージョン管理しています。   
tagpr の説明については以下の記事を参照

[リリース用のpull requestを自動作成し、マージされたら自動でタグを打つtagpr](https://songmu.jp/riji/entry/2022-09-05-tagpr.html)

スライド自体にもバージョンを埋め込んでいて、バージョンが上がると連動して更新されます。  

<img src="/update-version.png" class="h-60 rounded shadow" />

---
layout: two-cols-header
---

# tagprによるバージョン管理
動作イメージ

::left::

リリース用 PR  
https://github.com/k2tzumi/slidev-boilerplate/pull/4

![Release Pull Request](release-pr.png)

::right::

リリースノート自動生成
https://github.com/k2tzumi/slidev-boilerplate/releases/tag/v0.0.2

![Release note](release-note.png)

---

# GitHub Pagesへ自動Publish
スライド共有サイトを使わず、自前でスライドをホスティングできる！

SlideShare の広告が大変なことになっているので、スライドを自前で配信させたかったので GiHub Pages へ掲載するようにしました。  
tagpr によるバージョン管理と連動して、リリース用の PR がマージされると自動で Publish されるようになっています。  
実際に出来上がった内容はこちら  

https://k2tzumi.github.io/slidev-boilerplate

その他にも

- Google Tag Manager に対応して Google Analytics によるアクセス解析ができるようになっています
- OGP タグ対応でスライドのサムネを付きで SNS へ共有できます


---

# よく使うコマンドはMakefileから呼び出し
make コマンドは優秀なタスクランチャー

slidev の操作を行うコマンドをすぐ忘れてしまうので make コマンドを叩けばわかるようにしました。

```console
$ make
build                          Build slide
clean                          Delete slide
dev                            Run dev server
install                        Install packages
lint                           Run textlint
pdf                            Export PDF
publish                        Publish slide
upgrade                        Upgrades package.json
```

---

# テクニカルライティング用のLinter導入
typo の達人を回避する為に機械でチェックさせる

```console
$ make lint
npx textlint --cache slides.md

/Users/katsumi/workspace/about-slidev-boilerplate/slides.md
  142:31  error  ら抜き言葉を使用しています。                                                                    ja-technical-writing/no-dropping-the-ra
  143:26  error  一文に二回以上利用されている助詞 "に" がみつかりました。

次の助詞が連続しているため、文を読みにくくしています。

- "に"
- "に"

同じ助詞を連続して利用しない、文の中で順番を入れ替える、文を分割するなどを検討してください。
    ja-technical-writing/no-doubled-joshi
  207:9   error  【dict5】 "操作を行う"は冗長な表現です。"操作する"など簡潔な表現にすると文章が明瞭になります。
解説: https://github.com/textlint-ja/textlint-rule-ja-no-redundant-expression#dict5  ja-technical-writing/ja-no-redundant-expression

✖ 3 problems (3 errors, 0 warnings)

make: *** [.textlintcache] Error 1
```

---

# テクニカルライティング用のLinter導入
PR上でレビューコメントがされます

https://github.com/k2tzumi/about-slidev-boilerplate/pull/1#pullrequestreview-1761146122


<img src="/reviewdog.png" class="shadow rounded" />

---

# QRコードのアドオンを導入済み
QR コードでページ誘導するのは効果的

```xml
<QRCode width="180" height="180" value="https://twitter.com/katzchum" color="4329B9" image="Logo_of_X.svg" />
```

👆これだけで、👇こう表示されます

<QRCode width="180" height="180" value="https://twitter.com/katzchum" color="4329B9" image="Logo_of_X.svg" />

以下のライブラリを公開中  
https://www.npmjs.com/package/@katzumi/slidev-addon-qrcode

---

# CSSは外部ファイル化しておく
style.css のファイルに CSS を付け加える

<blockquote>
        <p>引用っぽいの</p>
</blockquote>

<br />

<div class="fusen">
付箋っぽいの<br />  
</div>

---

# Devcontainer対応
全てはクラウド環境に

nodejs 環境がローカルになくてもボタン一発で CodeSpace 上に環境が構築されます。  
出先で軽く修正。なんならプレゼンも可能です。

<img src="/codespace.png" class="h-100 rounded" />

---
layout: image-right
image: https://source.unsplash.com/collection/94734566/960x1080
---

# GitHub Actionsの設定方法について
いくつかの権限及び設定が必要にります

---
layout: default
---

# GitHub Actions権限追加
Workflow権限に書き込み＆PR作成を追加

https://github.com/{owner}/{repository}/settings/actions

![settings/actions](settings-actions.png)

---

# GitHub Pagesデプロイ設定
ソース設定

https://github.com/{owner}/{repository}/settings/pages

![settings/pages](settings-pages.png)

---
layout: two-cols-header
---

# 環境設定
GitHub Pagesのデプロイブランチ設定

https://github.com/{owner}/{repository}/settings/environments

::left::

github-pagesをクリック
![settings-environments](settings-environments.png)

::right::

`tagpr-from-*` をブランチ追加
![Deployment branches](deployment-branches.png)

---
layout: two-cols-header
---

# シークレット設定（オプション）
Google tag manager(Google Analytics)連携のシークレット追加

https://github.com/{owner}/{repository}/settings/secrets/actions/new

::left::

Repository secretsを追加

![Repository secrets](repository-secrets.png)

::right::

`GA_TRACKING_ID` にgoogleタグIDを設定
![New secret](new-secret.png)

---


# Special thanks！

- [Slidev](https://ja.sli.dev/)
- [tagpr](https://github.com/Songmu/tagpr)
- [textlint](https://github.com/textlint/textlint)
- [Reviewdog](https://github.com/reviewdog/reviewdog)
- [playwright](https://playwright.dev/)
- [qrcode-vue3](https://github.com/scholtz/qrcode-vue3)

---
layout: end
---

Fin.
