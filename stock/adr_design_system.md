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

### 導入事例

- material-ui

  - [ 事例一覧 ] (https://material-ui.com/ja/discover-more/showcase/ )

  [ react-admin ]( https://github.com/marmelab/react-admin )

  - 日本の例
  
    [ Hokan - 保険代理店様の営業を最適化 ](https://www.hkn.jp/)
      
    [ barks ](https://www.barks.jp/)

- React Spectrum
  
  (要調査)

### ドキュメント・資料について

- React Spectrum

CSS に関する props だと ソースコードコメントに MDN へのリンクが張られており、MDNはほぼ日本語化されているので、VSCodeから素早く有用な日本語情報へのリーチはしやすい。

.d.tsのソースマップ が作成されているようなので、VSCodeからコードが追えるようになっていると思われる(要検証)。(現在、自端末では動作確認はできていない)

[ tsconfig - declarationMap ]( https://www.typescriptlang.org/ja/tsconfig#declarationMap )

```
Declaration Map - declarationMap
元の.tsソースファイルにマップされる.d.tsのソースマップを生成します。

これにより、VS Code などのエディターは、Go to Definitionのような機能で元の.tsファイルにジャンプできるようになります。

プエジェクト参照機能を利用している場合、このオプションの有効化を強く推奨します。
```

- material-ui

公式ドキュメントに日本語訳があるにはあるが、[ コード部分が訳されていたり ](https://material-ui.com/ja/customization/globals/) 等、翻訳が校正されずに放置されてるのが散見されたりする(2-3年前から変わっていない) ので、あまり信用はできない。DeepL とかで、再翻訳したほうが質は高そう。

Hooks 以前の日付だが、英語の本が出ているようだ [ 2019/3/30 React Material-UI Cookbook: Build captivating user experiences using React and Material-UI (English Edition) Kindle版 ]( https://www.amazon.co.jp/React-Material-UI-Cookbook-captivating-experiences-ebook/dp/B07KJNQ44C
 )

- 所感

 material-ui の用途、見る人が限られている管理画面等が 殺風景 なので少し装飾したい、といったものや、OSSでデザインにコストかけたくない等、がほとんどと考えられ、日本語情報は「管理画面つくってみた」系ばかりで、情報の質が低く、Hooks以前の情報も大量に引っかかる為ノイズが多い。

 また、調べたいことのほどんどは各コンポーネントの props の使い方なので、ニッチすぎて Google検索だと、引っかからないか、ノイズばっかり引っかかる為、公式ドキュメントの質やコードの質のほうが重要になる。その点でかんがえると  props 一つ一つにMDN へのリンクが張られ、TSで書かれ、UNION型で型付されて補完もしやすい Spectrum のほうが優秀と個人的に考えている

### CSSカスタマイズ

- Spectrum

Adobe XD(UI/UXデザインツール) のPluginが提供されており、それを通じてデザインの変更が差し替えやすくなっている模様 (要検証)

[ Spectrum for Adobe XD plugin ]( https://spectrum.adobe.com/page/spectrum-xd-plugin/ )

  ```
  The Spectrum for Adobe XD plugin lets you use actual design system components in your XD projects, making it easy and fast to iterate on designs while still ensuring they’re up to date with the latest specs and looking like Adobe interfaces.

  --- 翻訳
  
  Spectrum for Adobe XDプラグインを使用すると、実際のデザイン・システム・コンポーネントをXDプロジェクトで使用できるようになるため、デザインの反復作業を簡単かつ迅速に行うことができ、最新の仕様とAdobeインターフェイスの外観を維持したまま、デザインを最新の状態に保つことができます。
  ```

- material-ui

[ material-ui - CSS ]( https://material-ui.com/ja/customization/globals/#css ) によれば、以下のように、Theme の Object のプロパティを上書きする方法で、CSSをカスタマイズ可能な模様。

```typescript
const theme = createMuiTheme({
  overrides: {
    MuiCssBaseline: {
      '@global': {
        html: {
          WebkitFontSmoothing: 'auto',
        },
      },
    },
  },
});

// ...
return (
  <ThemeProvider theme={theme}>
    <CssBaseline />
    {children}
  </ThemeProvider>
);
```
[ コンポーネントのカスタマイズ ]( https://material-ui.com/ja/customization/components/ )

CSS ファイルを上書きする方法は提供されていないようなので、デザイン変更時のデザイナが ts ファイルをいじるか、移植をする人員を割り当てる必要が発生するのでデザイン変更のコストが高くなることが予測される

有料テーマ、サポートはあるが、日本語対応はたぶんしていなさそう。 [ Premium themes ]( https://material-ui.com/store/?utm_source=docs&utm_medium=referral&utm_campaign=home-store ) [ Professional support (premium) ]( https://material-ui.com/getting-started/support/#professional-support-premium )

- 所感

  デザイナに外注等するなら、Spectrum 有利。プログラマーが多少カスタマイズする程度、なら material-ui が適しているかもしれない。

### 検索、トレンド比較

- Google 検索結果 

  React → 約 34900 万件

  React Spectrum → 約 126,00 万件
    ノイズが多そうなので Adobe React Spectrum → 約 198 万件
  
  React material-ui → 約 1580 万件

- トレンド比較

  https://trends.google.co.jp/trends/explore?date=today%203-m&q=React%20Spectrum,Material-UI,AntDesign,FluentUI

   Material-UI が優勢(目算で10倍程度?)

### ライセンス

  React Spectrum   Apache-2.0 License

  Material-UI      MIT License

  - [オープンソースライセンス、どれなら使っても良いの？？ ]( https://qiita.com/fate_shelled/items/a928709d7610cee5aa66 ) より抜粋

  - Apache License v2
  
    Apache Licenseであることの表示のみでOK！
    
    改変した場合には、その旨を表示する必要あり。
      特許条項あり
      配布されているOSSの中に特許が含まれていたら、それは無償で自由に実施してよい
      自身の特許がそのOSSに含まれていると主張した場合、そのOSSは使えない
      後出しジャンケンで特許料を徴収することを防いでいるのかと

  - MIT License

    作者の名前を記し、作者に一切の責任を求めない限り自由に扱える
      再配布時には著作権表示と本許諾表示（ソース内でもOK）
      無保証

  - 所感

    企業で使うなら、 Apache-2.0 License の  React Spectrum が 若干有利か?  

### カスタムコンポーネントの作りやすさ

- React Spectrum
  
  振る舞い部分を Hooks に切り出されているので、カスタムコンポーネントは、作りやすいと思われる

```typescript
import {useRadioGroupState} from '@react-stately/radio';

function RadioGroup(props) {
  let state = useRadioGroupState(props);

  return (
    <>
      <label>
        <input
          type="radio"
          name={state.name}
          checked={state.selectedValue === 'dogs'}
          onChange={() => state.setSelectedValue('dogs')}
        />
        Dogs
      </label>
      <label>
        <input
          type="radio"
          name={state.name}
          checked={state.selectedValue === 'cats'}
          onChange={() => state.setSelectedValue('cats')}
        />
        Cats
      </label>
    </>
  );
}

<RadioGroup
  defaultValue="dogs"
  onChange={(value) => alert(`Selected ${value}`)}
/>
```

- material-ui 

(要検証)

### コンポーネントの充実度

(要検証)

material-ui の方が多い印象。しかし、React Spectrum は、より大きな枠組みの [ Spectrum - Adobe’s design system ]( https://spectrum.adobe.com/ ) (XD File,CSS,WebComponents等のリソース集) の 一実装、という位置づけのようなので Spectrum design system 自体のコンポーネント数はもっと多い(React Spectrum の実装範囲は目算で 6-7割 位に見える) 

### マルチデバイス対応

(要検証)

### a11y対応

(要検証)

### TypeScro.ipt

(要検証)

### PoC 適性

(要検証)

### SSG,SSR

(要検証)

### その他 コンポーネントライブラリ

[ ant-design ]( https://github.com/ant-design/ant-design/ )

[ Semantic-UI-React ]( https://github.com/Semantic-Org/Semantic-UI-React )

[ react-bootstrap ]( https://github.com/react-bootstrap/react-bootstrap )

### その他 情報

[ 開発者のためのReactJSロードマップ ]( https://itnews.org/news_contents/reactjs-roadmap-for-developers-2824 )

[ Best CSS Frameworks in 2020 ]( https://dev.to/theme_selection/best-css-frameworks-in-2020-1jjh )

## git clone 集

git clone https://github.com/adobe/react-spectrum.git

git clone https://github.com/tailwindlabs/tailwindcss.git

git clone https://github.com/microsoft/fluentui.git

git clone https://github.com/mui-org/material-ui.git

git clone https://github.com/ant-design/ant-design.git

git clone https://github.com/react-bootstrap/react-bootstrap.git

git clone https://github.com/Semantic-Org/Semantic-UI-React.git
