# nuxt-sample-project

## 目的
nuxtの自分がよく使うサンプルプロジェクトを管理するためのものです。<br>
(Nuxtのvue3対応版がきたらこちらは、`old/v2`ブランチに移動させます)

## プロジェクト設定
<img width="575" alt="スクリーンショット 2020-11-18 0 11 47" src="https://user-images.githubusercontent.com/47517002/99410409-caf52100-2935-11eb-83c7-c9e3fa31a8f8.png">


## 作成後に行うこと
1. `yarn add stylelint-prettier --dev`がないので追加

1. `yarn add @nuxtjs/storybook --dev`を実行してstorybook導入

1. `"storybook": "yarn nuxt storybook"`をscriptsに追加("test"コマンドの下)

1. 以下を.gitignoreに追加
   ```
    # storybook
    .nuxt-storybook
    storybook-static
   ```
   
1. 以下をscriptsに追加
   ```
    "lint-js": "eslint --ext .js,.vue .",
    "lint-style": "stylelint \"**/*.vue\" \"**/*.css\"",
    "lint-js:fix": "eslint --ext .js,.vue . --fix",
    "lint-style:fix": "stylelint \"**/*.vue\" \"**/*.css\" --fix",
    "lint:check": "yarn lint-js & yarn lint-style",
    "lint:fix": "yarn lint-js:fix && yarn lint-style:fix",
   ```
1. `yarn storybook`を実行(もし、lintエラーが出たら、`yarn lint:fixで修正`)

1. `yarn dev`、`yarn generate`を正常に行えたら終わり
   
## scripts
- lint(eslint, stylelint, prettierが走ります)
  - lintのルールを満たさないところを出力<br>
   `yarn lint:check`

  - lintの機能で自動修正<br>
   `yarn lint:fix`

- storybook
  - ローカルで閲覧<br>
   `yarn storybook`

  - ビルド<br>
   `yarn storybook build`

## 各ドキュメント
- [nuxt](https://nuxtjs.org/)
- [eslint](https://eslint.org/)
- [stylelint](https://stylelint.io/)
- [jest](https://jestjs.io/ja/)
- [vue-test-utils](https://vue-test-utils.vuejs.org/ja/)
- [nuxt-community/storybook](https://storybook.nuxtjs.org/)


