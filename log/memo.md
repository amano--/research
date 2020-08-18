T字型ERやREA(en.m.wikipedia.org/wiki/Resources…)やEvent Stormingのいずれもイベントを分析に使うモデリングのテクニックです。


話題になってるOOPartsの技術スタックを外から見える範囲で調べてみたけど、古い業界に対してバリバリモダンな技術で攻めてる、すごい。
React + emotion + tailwindcss
* Firebase(Authentication + Firestore)
* Stripe
* imgix
* Algoria

[ Rendering on the Web - Web上のレンダリング ]( https://developers.google.com/web/updates/2019/02/rendering-on-the-web?hl=ja )

[ TypeScript 練習問題集(Practice TypeScript) latest update(2020/1/18) ]( https://gist.github.com/kenmori/8cea4b82dd12ad31f565721c9c456662 )

[ 今週大幅にリニューアルされた Next.js のチュートリアルをどこよりも早く全編和訳しました ]( https://qiita.com/thesugar/items/01896c1faa8241e6b1bc )

[ The React Profiler API ]( https://addyosmani.com/blog/profiling-react-js/ )

[ Restyle library provides a type-enforced system for building UI components in React Native with TypeScript. ]( https://github.com/Shopify/restyle )

[ React Summit Remote Edition まとめ(前編) ]( https://blog.naturalclar.dev/react-summit-remote-summary-part-1/ )


[ Concurrent Mode時代のReact設計論 (1) Concurrent Modeにおける非同期処理 ]( https://qiita.com/uhyo/items/4a6315bfccf387407631 )

[ 2020年初頭における Next.js をベースとしたフロントエンドの環境構築 ]( https://qiita.com/syuji-higa/items/931e44046c17f53b432b )

"zackkrida/next-codegen: Fast API route and page generation for Next.js projects" 

https://github.com/zackkrida/next-codegen

[ Github - oukayuka ]( https://github.com/oukayuka )
[ 技術書博App ]( https://github.com/gishohaku/gishohaku-app ) 
[ Reactを学ぶのに役立つ学習リソースをまとめてみた ]( https://kirohi.com/react-study-resources )

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
[ React 公式 / JSX を深く理解する ]( https://ja.reactjs.org/docs/jsx-in-depth.html#user-defined-components-must-be-capitalized )

配列は ReadonlyArray<T> にする [ readonlyな配列とタプル ]( https://qiita.com/uhyo/items/e2fdef2d3236b9bfe74a#readonly%E3%81%AA%E9%85%8D%E5%88%97%E3%81%A8%E3%82%BF%E3%83%97%E3%83%AB )


### 公式サイト
[ React 公式 Getting Started ]( https://ja.reactjs.org/docs/getting-started.html )

### 便利ツール
[ オンライン Babel コンパイラ ]( https://babeljs.io/repl/#?presets=react&code_lz=GYVwdgxgLglg9mABACwKYBt1wBQEpEDeAUIogE6pQhlIA8AJjAG4B8AEhlogO5xnr0AhLQD0jVgG4iAXyJA )

### Typescript関連
・ 初級
[ 仕事ですぐに使えるTypeScript ]( https://future-architect.github.io/typescript-guide/ )
[ TypeScript Deep Diveの日本語版 ]( https://typescript-jp.gitbook.io/deep-dive/ )

・ 型関連
[ TypeScriptの型入門 ]( https://qiita.com/uhyo/items/e2fdef2d3236b9bfe74a )

[ TypeScriptの型初級 ]( https://qiita.com/uhyo/items/da21e2b3c10c8a03952f )
- conditional types と mapped types について詳しく解説されている
- ** [ TypeScriptの型初級 / 標準ライブラリの型 ]( https://qiita.com/uhyo/items/da21e2b3c10c8a03952f#%E6%A8%99%E6%BA%96%E3%83%A9%E3%82%A4%E3%83%96%E3%83%A9%E3%83%AA%E3%81%AE%E5%9E%8B ) は必読 **

``` typescript
function func(arg1: number | string, arg2?: number): number {
  if ('number' === typeof arg1) {
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
[ TypeScript 3.7のOptinal Chainig とNullish Coalescingを使ってみた ]( https://qiita.com/YukiIchika/items/0c2bd4703aa1396ad8f8 )

### React 型チェック Tips
[ React開発において便利なTypeScriptの型まとめ ]( https://qiita.com/markey/items/134386ee98b277f181f7 )
[ Reactコンポーネントchildren属性の型の書き方 ]( https://qiita.com/Anders/items/8ce894d548ff028259a8 )

### Reactコンポーネントライブラリ

[ chakra-ui ]( https://chakra-ui.com/ )
- [ OpenChakra ]( https://openchakra.app/ ) という WYSWIG エディタ があるので Pageは作りやすいかも。



children: React.ChildrenArray<React.Element<typeof TabBarIOSItem>>,

Null合体演算子( Nullish Coalescing ) と Optional Chaining 


Tagged Union
[ TypeScriptで関数型プログラミングしたい勢に推したいPipeline operatorの良さ ]( https://hachibeechan.hateblo.jp/entry/pipeline-operator-will-be-good-friend-of-typescript )

Event Soursing

[ イミュータブルデータモデル ]( https://scrapbox.io/kawasima/%E3%82%A4%E3%83%9F%E3%83%A5%E3%83%BC%E3%82%BF%E3%83%96%E3%83%AB%E3%83%87%E3%83%BC%E3%82%BF%E3%83%A2%E3%83%87%E3%83%AB )


[ zod - Typescript-first schema validation with static type inference ]( https://github.com/vriad/zod )


それが、型引数を解決しないと引数の数が定まらないパターンがあります

https://www.typescriptlang.org/play/#code/GYVwdgxgLglg9mABKSAeA0gPgBQGsBci6ANIgHQUCGATgOYDOh6iApgB5QtgAm9i9UajDC1EAfkQBtALqJCk9NICUiAN4BfAFAB6bYji5NKCNgBEwOHFNKA3EfAmAjACYAzABZSAVgBsAdgAOW00dPRZqajhqe0gzCytSF1dg42wk92CgA

function func<K>(k: K, ...args: K extends string ? [] : [K]) {}
// ok
func("foo");
func(1234, 5678);

// error
func("foo", 123);
func(1234);


// 株式会社アイビスの郵便番号検索APIを使用しています：
// http://zipcloud.ibsnet.co.jp/doc/api


FaaS視点で各種サービスの分布を表すと

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

expoのリリースチャンネル、いまいち使い分けがわからなくなってきたぞ？TestFlightに上げるときとかstaging環境につなぐバージョンはどう分けるべきか

頑張って！！！（僕も答えを持っていない）
もうバージョンと同じ名前のリリースチャンネルを用意するしかないのではと思い詰めてしまっている。

productionとかやらずにバージョン毎にリリースチャンネルを用意するみたいな？

設定の切り分けみたいなのってバージョン＝リリースチャンネルのときにどうするの？マッピングみたいなのでも作る感じ？

環境変数で切り替えられるようにしといて、publishするとき（＝バンドルファイルのビルド時）に環境変数を与えれば切り替えられますです
あー、コード中のConstants.manifest.releaseChannelで切り分けすることを想定してた。確かに環境変数を渡すのもあるのか・・・
OTAに関しては割とオマケレベルでstagingでもそれほどヘビーユースしてなかった・・・

なるほどなるほど。release channelはOTAのときに効いてくるやつなので、もし運用に困るようならオフにする手もありそう。（そのへんもろもろ含めて僕も答えを持ってない）

なんか確かに、いわゆるNODE_ENVの切り替え的なことをするのにrelease channel頼るのはもしかしたら過大なのかもしれんのか（とはいえ何を使おうかという感じあるが）

特にオススメできるほど確信を持って使ってるわけではないけど、僕の用途だとbabel-plugin-transform-inline-environment-variablesでだいたい回ってる。

releaseChannelで使い回すのとtransform-inline-environment-variablesだと運用的にはCLIから渡すのであんまり変わらないように思えるけどそうでも

明示的にpublish（バンドルファイルのアップロード）をオフにするのであればあんまり変わらないと思う。
デフォルトだとビルド時に必ずアップロードが発生しちゃうので、チャンネル設定次第では思わぬタイミングでユーザーの手元に新しいアプリが届いちゃったりして、ちょっと怖い。
