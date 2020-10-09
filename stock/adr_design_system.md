# React コンポーネントライブラリ選定における 調査、検討 2020/10

## 比較記事集

- かなりの数のコンポーネントライブラリが網羅されたリンク集 → [ awesome-react ‐ component-libraries ]( https://github.com/enaqx/awesome-react#react-component-libraries )

- [ Reactでのコンポーネントライブラリをまとめる ]( https://coders-shelf.com/react-component-libraries/ ) - 2020/2/13

```
Material UI (Githubスター数：54k)
Ant-design (Githubスター数：56k)
React Bootstrap (Githubスター数：17k)
Semantic UI React (Githubスター数：11k)
```
  - 結論
    
    私のおすすめ度としてはMaterial UI > Semantic UI > React Bootstrap > Ant Designという感じです。  

- [ Top Component Libraries for React in Comparison ]( https://www.tderflinger.com/en/top-components-libs-comparison )

  - 結論(翻訳)

    デザインの好みは人それぞれなので、大手のデザイン系のどれかを使うことで良い感じになります。Semantic UI Reactの将来は、現在活発に活動しているコミュニティにかかっています。なので、独立したプロジェクトをサポートしたいのであれば、Semantic UI Reactを選ぶのが良いでしょう。

- [ Comparing popular React component libraries ]( https://blog.logrocket.com/comparing-popular-react-component-libraries/ )


## 検討対象にしたFW

上記比較サイトやその他情報をもとに検討した結果、今のところ一番良いと考えているのは Adobe製の [ React Spectrum ]( https://github.com/adobe/react-spectrum )。次点で [ material-ui ]( https://github.com/mui-org/material-ui )、[ fluentui ]( https://github.com/microsoft/fluentui ) 


また、関連するものとして、CSSのフレームワークである [ tailwindcss ]( https://github.com/tailwindlabs/tailwindcss ) にも少し触れておく。


### React Spectrum  (Githubスター数：3.6k)

- 概要 

  [ React Spectrum - github ]( https://github.com/adobe/react-spectrum )

  [ Adobe製デザインシステム「React Spectrum」がすごいので紹介したい ]( https://qiita.com/so99ynoodles/items/bc924b7ee8c265b09723 ) 
  
- 所感

比較的最近の 2020/7/15 にリリースされた Adobe製のFW。そのため比較記事で登場することは、ほぼない。しかしながら、コードベースが新しいだけあって Hooks に最適化されているように感じる。React Hooks のリリースは 2019/4 なので、それ以前から存在しているFWは Class コンポーネントでの実装がほとんどで、 Hooksは後付け実装になっている。

Hooks はコンポーネント設計を大きくかえたため、Hooks以後に実装されたこのFWとその他FWをコードで比較すると、根本的に違ったりするので、なにかの調査でコードを追う必要に迫られた場合、このFWのコード方がスキルセット的に読みやすく、学びが多いため、優位性があると考える。

また一般人を相手にしたシステムだとすれば、アクセシビリティ(a11y) 対応も考える必要があり、それに対応している点も評価できる。

デザイン変更の容易性を比較すると、[materialデザイン]( https://ja.wikipedia.org/wiki/%E3%83%9E%E3%83%86%E3%83%AA%E3%82%A2%E3%83%AB%E3%83%87%E3%82%B6%E3%82%A4%E3%83%B3 ) に 寄った material-ui 、Office365寄り? の fluentui に比べれば、デザイン変更容易性への配慮が感じられる(要検証)

### FluentUI (Githubスター数：9.6k)

- 概要 
  
[ fluentui ]( https://github.com/microsoft/fluentui )

- [ Fluent UI - Microsoft社製のReact向けUIコンポーネント ]( https://www.moongift.jp/2020/04/fluent-ui-microsoft%E7%A4%BE%E8%A3%BD%E3%81%AEreact%E5%90%91%E3%81%91ui%E3%82%B3%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%8D%E3%83%B3%E3%83%88/ )

- 所感

Office365 で使っている ReactComponent集(旧名 OfficeUIFabric ) のようだ。TSで作成されているがやはりコードベースが古い。MicroSoft が作成しているという安心感はあるが、Spectrum に対しての優位性はないと考える

### material-ui  (Githubスター数：61.6k)

- 概要 

[ material-ui ]( https://github.com/mui-org/material-ui )
  
- 所感

Reactコンポーネントライブラリでは、おそらく一番有名で実績があるものだが、JSで書かれており、その他のことを考慮しても Spectrum に対しての優位性はないと考える

### tailwindcss

[ tailwindcss - github ]( https://github.com/tailwindlabs/tailwindcss )

- [ Tailwind CSS入門 - フロントエンドで素晴らしい開発体験を得るために ]( https://panda-program.com/posts/recommend-developers-use-tailwind-css )

- [ 翻訳：CSSユーティリティクラスと「関心の分離」（いかにしてユーティリティファーストにたどり着いたか） ](https://yuheiy.hatenablog.com/entry/2020/05/25/021342)

### 総評

Spectrum の所感でも述べたように、Hooks 登場以前と以後には大きな隔たりがあり、必然的に Hooks 以後に登場した Spectrum に比べると どのFW を選んでも大差はないといえるだろう。

また、その他条件(アクセシビリティ、デザイン変更の容易性、コード理解の容易性、等) を勘案しても Spectrum に優位性がある、というのが今のところの結論。


### その他 コンポーネントライブラリ

[ ant-design ]( https://github.com/ant-design/ant-design/ )

[ Semantic-UI-React ]( https://github.com/Semantic-Org/Semantic-UI-React )

[ react-bootstrap ]( https://github.com/react-bootstrap/react-bootstrap )

## git clone 集

git clone https://github.com/adobe/react-spectrum.git

git clone https://github.com/tailwindlabs/tailwindcss.git

git clone https://github.com/microsoft/fluentui.git

git clone https://github.com/mui-org/material-ui.git

git clone https://github.com/ant-design/ant-design.git

git clone https://github.com/react-bootstrap/react-bootstrap.git

git clone https://github.com/Semantic-Org/Semantic-UI-React.git

