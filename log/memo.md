function compose<T0>(): (x: T0) => T0;
function compose<T0, T1>(f0: (x: T0) => T1): (x: T0) => T1;
function compose<T0, T1, T2>(f0: (x: T0) => T1, f1: (x: T1) => T2): (x: T0) => T2;
function compose<T0, T1, T2, T3>(
f0: (x: T0) => T1,
f1: (x: T1) => T2,
f2: (x: T2) => T3,
): (x: T0) => T3;
function compose<T0, T1, T2, T3, T4>(
f0: (x: T0) => T1,
f1: (x: T1) => T2,
f2: (x: T2) => T3,
f3: (x: T3) => T4,
): (x: T0) => T4;
function compose<T0, T1, T2, T3, T4, T5>(
f0: (x: T0) => T1,
f1: (x: T1) => T2,
f2: (x: T2) => T3,
f3: (x: T3) => T4,
f4: (x: T4) => T5,
): (x: T0) => T5;
function compose<T0, T1, T2, T3, T4, T5, T6>(
f0: (x: T0) => T1,
f1: (x: T1) => T2,
f2: (x: T2) => T3,
f3: (x: T3) => T4,
f4: (x: T4) => T5,
f5: (x: T5) => T6,
): (x: T0) => T6;
function compose<T0, T1, T2, T3, T4, T5, T6, T7>(
f0: (x: T0) => T1,
f1: (x: T1) => T2,
f2: (x: T2) => T3,
f3: (x: T3) => T4,
f4: (x: T4) => T5,
f5: (x: T5) => T6,
f6: (x: T6) => T7,
): (x: T0) => T7;
function compose<T0, T1, T2, T3, T4, T5, T6, T7, T8>(
f0: (x: T0) => T1,
f1: (x: T1) => T2,
f2: (x: T2) => T3,
f3: (x: T3) => T4,
f4: (x: T4) => T5,
f5: (x: T5) => T6,
f6: (x: T6) => T7,
f7: (x: T7) => T8,
): (x: T0) => T8;
function compose<T0, T1, T2, T3, T4, T5, T6, T7, T8, T9>(
f0: (x: T0) => T1,
f1: (x: T1) => T2,
f2: (x: T2) => T3,
f3: (x: T3) => T4,
f4: (x: T4) => T5,
f5: (x: T5) => T6,
f6: (x: T6) => T7,
f7: (x: T7) => T8,
f8: (x: T8) => T9,
): (x: T0) => T9;
function compose(...fs: ((x: any) => any)[]): (x: any) => any {
return (x: any) => {
let val = x;
for (const f of fs) {
val = f(val);
}
return val;
};
}

Q: union string 型 の 配列 から ajv valid な json schema 作るときに型の補完が効かなくて辛いのですがどうしたらいいですか？

A: union type をコピペして | を , に置換するのぢゃ

1. JSON Schema をツール (stoplight 等) で設定し、GodeGen 系ツールで、TS,Java 等必要なコードを自動生成する。

   ※ 未検証

【 利点 】

- マルチ言語対応な汎用な型定義なので、クライアント、サーバーのコードを共通化しやすい。

【 欠点 】

- Web クライアント側(JS) で、違うバリデーションルールを適用する場合、2 つ定義する必要がある
- stoplight 等のツールを使っても、定義のコストが高めに感じる
- JSON Schema if then else 部分の定義方法が難しいと感じる。
- 多少複雑な型を設定しようとすると、どう設定するのが良いか迷いやすいと思われる。
  → 定義工数が高いと感じるみち stoplight を使うようなので、スキルセット的にはあまり問題にならないのかもしれない。

2. TS で型定義し、ツール( [quicktype](https://github.com/quicktype/quicktype) ) で JSON Schema を生成し、バリデーションの設定を追記する。

【 利点 】

- 型定義が JSON Schema よりは書きやすい。
- 多少複雑な型でも対応しやすい。
- 型安全に定義できる
- IDE で静的解析可能になり、事前にエラーを検出しやすい。

- JSON Schema if then else 部分も何かしらの型定義を基に自動生成できるようにできれば、JSON Schema の生成コストも抑えられるようになる。

【 欠点 】

- TS のスキルセットが必要

- 生成後の JSON Schema を個別に修正する必要がある場合、型定義と 2 重定義状態になるのでスキーマ管理が複雑化する恐れがある。

ビジネスルールを表現する５点セット。
値オブジェクト（金額、数量、日付、地点、...)
区分オブジェクト(商品区分、サービス区分、状態区分、...)
範囲オブジェクト(価格帯、期間、地域、...)
コレクションオブジェクト(順序・集合・写像）
表オブジェクト（価格表、判定表、...)

project
subject
object
reject
inject
deject
eject

ject つながり
みんな投げる

前へ
下へ
そっちへ
返す
中に
逆へ
外に

produce
reduce
induce
deduce
educe

duce つながり
みんな引っ張る

前に
後ろに
中に
外に
強く

[ マルチコメントビューア ](https://ryu-s.github.io/app/multicommentviewer)

[ DeepL ] ( https://www.deepl.com/ja/translator )

- 英和
  - [ Webilio ] ( https://ejje.weblio.jp/ )
- 英英
- [ longman ] (https://www.ldoceonline.com)
- [ oxford ] (https://www.oxfordlearnersdictionaries.com)
- [ cambridge ] (https://dictionary.cambridge.org/)
- 語源辞書
  - [ etym ] (https://www.etymonline.com/)
- 類語
  - [ thesaurus ](https://www.thesaurus.com/)

デザイン思考が世界を変える
エンジニアのためのデザイン思考入門
デザインシンキング・プレイブック
リーン・スタートアップ
Running Lean
リーン顧客開発
エクストリームプログラミング
エッセンシャルスクラム
カンバン仕事術

コードには How
テストコードには What
コミットログには Why
コードコメントには Why not

コードの最後まで実行されてから Unhandled Rejection になったのは、Promise が microtask として扱われているから、という説明ではダメなのだろうか

Bubble.io でフロントエンドをノーコード開発してみた。
API Connector プラグインとデザイン画面の insert dynamic data の組み合わせはほんと便利。
API で取得した JSON の構造を解析したデータ項目のサジェションが使いやすい。
記号を使ったコード的な記法がまったくないのが、よい感じ。

hasura の GraphQL 経由のより、blitz の isomorphism の方が TS フレンドリーではある。クラサバどっちも TS に縛られはする

- アランケイのメッセージ指向(Smalltalk)?
  - ビャーネ・ストラウストラップのクラス指向(C++)?
  - バートランドメイヤーのインターフェース指向(Java/C#/Rust)?
  - Self から始まったプロトタイプベース(Self/Javascript)?
  - 「あなたのオブジェクト指向はどこから？」でスタートするのが良いかも()

Function:
Value -> Value

Type Class:
Type -> Value

Type-level Programming:
Type -> Type

Dependent Types:
Value -> Type

    github.com で便利なショートカット。よく忘れるので書いとく。

t - ファイル検索
l - 指定行数にジャンプ
y - ファイルの URL をパーマリンクにする
b - blame 表示
? - ショートカット一覧を表示

bit.ly/322H3E9

もう何ヶ月も型パズル解いてないけど
型パズルと戦うときに初めにやることは
noErrorTruncation: true と tsconfig に書くことだった気がする

list
.groupBy(_.key)
.toList
.sortBy(_._1)
.map(_._2.map(_.value).sum)

みたいな事してませんか？ 実はこれ簡単に書けますよ

list.foldMap(e => SortedMap(e.key -> e.value)).values

そう、モノイドならね

type Join<T extends readonly (string | number | boolean | bigint)[], D extends string> =
T extends readonly [] ? '' :
T extends readonly [unknown] ? `${T[0]}` :
T extends readonly [unknown, ...infer U] ? `${T[0]}${D}${Join<U, D>}` :
string;

function join<
T extends readonly (string | number | boolean | bigint)[],
D extends string

> (arr: T, del: D) {

    return arr.join(del) as Join<T, D>

}

const word = join(['Hello', 'World'] as const, ' x ')

天然のレガシーコードは、手持ちのスキルでなんとか先に進めようという真面目さとか必死さ、ある種の善意から生まれる。養殖物のレガシーコードは、研修や本のためにレガシーコードを書いてやろうというある種の悪意から生まれる。悪意は善意を超えられない……

T 字型 ER や REA(en.m.wikipedia.org/wiki/Resources…)や Event Storming のいずれもイベントを分析に使うモデリングのテクニックです。

話題になってる OOParts の技術スタックを外から見える範囲で調べてみたけど、古い業界に対してバリバリモダンな技術で攻めてる、すごい。
React + emotion + tailwindcss

- Firebase(Authentication + Firestore)
- Stripe
- imgix
- Algoria

[ Rendering on the Web - Web 上のレンダリング ](https://developers.google.com/web/updates/2019/02/rendering-on-the-web?hl=ja)

[ TypeScript 練習問題集(Practice TypeScript) latest update(2020/1/18) ](https://gist.github.com/kenmori/8cea4b82dd12ad31f565721c9c456662)

[ 今週大幅にリニューアルされた Next.js のチュートリアルをどこよりも早く全編和訳しました ](https://qiita.com/thesugar/items/01896c1faa8241e6b1bc)

[ The React Profiler API ](https://addyosmani.com/blog/profiling-react-js/)

[ Restyle library provides a type-enforced system for building UI components in React Native with TypeScript. ](https://github.com/Shopify/restyle)

[ React Summit Remote Edition まとめ(前編) ](https://blog.naturalclar.dev/react-summit-remote-summary-part-1/)

[ Concurrent Mode 時代の React 設計論 (1) Concurrent Mode における非同期処理 ](https://qiita.com/uhyo/items/4a6315bfccf387407631)

[ 2020 年初頭における Next.js をベースとしたフロントエンドの環境構築 ](https://qiita.com/syuji-higa/items/931e44046c17f53b432b)

"zackkrida/next-codegen: Fast API route and page generation for Next.js projects"

https://github.com/zackkrida/next-codegen

[ Github - oukayuka ](https://github.com/oukayuka)
[ 技術書博 App ](https://github.com/gishohaku/gishohaku-app)
[ React を学ぶのに役立つ学習リソースをまとめてみた ](https://kirohi.com/react-study-resources)

### DDD

git clone https://github.com/little-hands/ddd-examples.git
git clone https://github.com/system-sekkei/isolating-the-domain

### React

git clone https://github.com/oukayuka/ReactFirebaseBook.git

### React Hooks

git clone https://github.com/erukiti/react-hooks-without-debt.git

### Typescript project template

git clone https://github.com/syuji-higa/template-nextjs.git

### Next.js

git clone https://github.com/gishohaku/gishohaku-app.git

cd ReactFirebaseBook/05-react/mangarel-demo/
yarn install

#container {
grid-template:
"areaA areaB areaC" 100px
"areaD areaE areaF" 100px
/ 200px 200px 200px;
}

### コーディング規約

ユーザ定義のコンポーネントの名前は大文字で始めること
[ React 公式 / JSX を深く理解する ](https://ja.reactjs.org/docs/jsx-in-depth.html#user-defined-components-must-be-capitalized)

配列は ReadonlyArray<T> にする [ readonly な配列とタプル ](https://qiita.com/uhyo/items/e2fdef2d3236b9bfe74a#readonly%E3%81%AA%E9%85%8D%E5%88%97%E3%81%A8%E3%82%BF%E3%83%97%E3%83%AB)

### 公式サイト

[ React 公式 Getting Started ](https://ja.reactjs.org/docs/getting-started.html)

### 便利ツール

[ オンライン Babel コンパイラ ](https://babeljs.io/repl/#?presets=react&code_lz=GYVwdgxgLglg9mABACwKYBt1wBQEpEDeAUIogE6pQhlIA8AJjAG4B8AEhlogO5xnr0AhLQD0jVgG4iAXyJA)

### Typescript 関連

・ 初級
[ 仕事ですぐに使える TypeScript ](https://future-architect.github.io/typescript-guide/)
[ TypeScript Deep Dive の日本語版 ](https://typescript-jp.gitbook.io/deep-dive/)

・ 型関連
[ TypeScript の型入門 ](https://qiita.com/uhyo/items/e2fdef2d3236b9bfe74a)

[ TypeScript の型初級 ](https://qiita.com/uhyo/items/da21e2b3c10c8a03952f)

- conditional types と mapped types について詳しく解説されている
- ** [ TypeScript の型初級 / 標準ライブラリの型 ](https://qiita.com/uhyo/items/da21e2b3c10c8a03952f#%E6%A8%99%E6%BA%96%E3%83%A9%E3%82%A4%E3%83%96%E3%83%A9%E3%83%AA%E3%81%AE%E5%9E%8B) は必読 **

```typescript
function func(arg1: number | string, arg2?: number): number {
  if ("number" === typeof arg1) {
    return arg1;
  } else {
    return Number.parseInt(arg1) + arg2!;
  }
}
/*
else側のarg2!が目に付きますが、この!後置演算子はTypeScript独自のもので、型から強制的にnullやundefinedを取り除くダウンキャストの演算子です。
arg1が文字列であると判明した時点でオーバーロードの2番目が選択されていることは明らかなので、arg2がundefinedでないことは分かるのですが、
残念ながらTypeScriptはそこまで賢くないのでarg2がundefinedにならないことを見抜くことはできません。そのために、自分でアノテートしています。
*/
```

・ 特殊な記法
[ TypeScript 3.7 の Optinal Chainig と Nullish Coalescing を使ってみた ](https://qiita.com/YukiIchika/items/0c2bd4703aa1396ad8f8)

### React 型チェック Tips

[ React 開発において便利な TypeScript の型まとめ ](https://qiita.com/markey/items/134386ee98b277f181f7)
[ React コンポーネント children 属性の型の書き方 ](https://qiita.com/Anders/items/8ce894d548ff028259a8)

### React コンポーネントライブラリ

[ chakra-ui ](https://chakra-ui.com/)

- [ OpenChakra ](https://openchakra.app/) という WYSWIG エディタ があるので Page は作りやすいかも。

children: React.ChildrenArray<React.Element<typeof TabBarIOSItem>>,

Null 合体演算子( Nullish Coalescing ) と Optional Chaining

Tagged Union
[ TypeScript で関数型プログラミングしたい勢に推したい Pipeline operator の良さ ](https://hachibeechan.hateblo.jp/entry/pipeline-operator-will-be-good-friend-of-typescript)

Event Soursing

[ イミュータブルデータモデル ](https://scrapbox.io/kawasima/%E3%82%A4%E3%83%9F%E3%83%A5%E3%83%BC%E3%82%BF%E3%83%96%E3%83%AB%E3%83%87%E3%83%BC%E3%82%BF%E3%83%A2%E3%83%87%E3%83%AB)

[ zod - Typescript-first schema validation with static type inference ](https://github.com/vriad/zod)

それが、型引数を解決しないと引数の数が定まらないパターンがあります

https://www.typescriptlang.org/play/#code/GYVwdgxgLglg9mABKSAeA0gPgBQGsBci6ANIgHQUCGATgOYDOh6iApgB5QtgAm9i9UajDC1EAfkQBtALqJCk9NICUiAN4BfAFAB6bYji5NKCNgBEwOHFNKA3EfAmAjACYAzABZSAVgBsAdgAOW00dPRZqajhqe0gzCytSF1dg42wk92CgA

function func<K>(k: K, ...args: K extends string ? [] : [K]) {}
// ok
func("foo");
func(1234, 5678);

// error
func("foo", 123);
func(1234);

// 株式会社アイビスの郵便番号検索 API を使用しています：
// http://zipcloud.ibsnet.co.jp/doc/api

FaaS 視点で各種サービスの分布を表すと

↑Opinionated/Ease-of-use

- Netlify Functions

- Cloud Functions for Firebase

- Google Cloud Functions

- AWS Lambda

↓Customizable/Complex

という印象

const Foo = {
Bar: [{
A: 'value1'
}],
Baz: [{
A: 'value2'
},{
A: 'value3'
}]
} as const

から 'value1' | 'value2' | 'value3' の型を作れ。
っていう応用が必要になってて詰んでる…

const Foo = {
Bar: [{
A: 'value1'
}],
Baz: [{
A: 'value2'
},{
A: 'value3'
}]
} as const

type A = typeof Foo[keyof typeof Foo][number]["A"]

expo のリリースチャンネル、いまいち使い分けがわからなくなってきたぞ？TestFlight に上げるときとか staging 環境につなぐバージョンはどう分けるべきか

頑張って！！！（僕も答えを持っていない）
もうバージョンと同じ名前のリリースチャンネルを用意するしかないのではと思い詰めてしまっている。

production とかやらずにバージョン毎にリリースチャンネルを用意するみたいな？

設定の切り分けみたいなのってバージョン＝リリースチャンネルのときにどうするの？マッピングみたいなのでも作る感じ？

環境変数で切り替えられるようにしといて、publish するとき（＝バンドルファイルのビルド時）に環境変数を与えれば切り替えられますです
あー、コード中の Constants.manifest.releaseChannel で切り分けすることを想定してた。確かに環境変数を渡すのもあるのか・・・
OTA に関しては割とオマケレベルで staging でもそれほどヘビーユースしてなかった・・・

なるほどなるほど。release channel は OTA のときに効いてくるやつなので、もし運用に困るようならオフにする手もありそう。（そのへんもろもろ含めて僕も答えを持ってない）

なんか確かに、いわゆる NODE_ENV の切り替え的なことをするのに release channel 頼るのはもしかしたら過大なのかもしれんのか（とはいえ何を使おうかという感じあるが）

特にオススメできるほど確信を持って使ってるわけではないけど、僕の用途だと babel-plugin-transform-inline-environment-variables でだいたい回ってる。

releaseChannel で使い回すのと transform-inline-environment-variables だと運用的には CLI から渡すのであんまり変わらないように思えるけどそうでも

明示的に publish（バンドルファイルのアップロード）をオフにするのであればあんまり変わらないと思う。
デフォルトだとビルド時に必ずアップロードが発生しちゃうので、チャンネル設定次第では思わぬタイミングでユーザーの手元に新しいアプリが届いちゃったりして、ちょっと怖い。
