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
