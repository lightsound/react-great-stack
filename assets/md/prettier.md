## prettier

+++

コードフォーマッター  
エディタ連携して保存時に発動させると最強

+++

問: eslint --fix でよくね？

答: prettier でしか整形できない項目もある

+++

例えば max-len  
eslint はアラートを出すだけ

```javascript
// prettier前
// prettier-ignore
foo(reallyLongArg(), omgSoManyParameters(), IShouldRefactorThis(), isThereSeriouslyAnotherOne());
```

```javascript
// prettier後
foo(
  reallyLongArg(),
  omgSoManyParameters(),
  IShouldRefactorThis(),
  isThereSeriouslyAnotherOne()
);
```

+++

max-len だけでなく色々設定できる  
詳しくは[公式ページ](https://prettier.io/docs/en/configuration.html) を参照

+++

eslint と設定が被るのでは？

（例）  
eslint は max-len:100  
prettier は max-len:80

+++

[prettier-eslint](https://github.com/prettier/prettier-eslint)  
prettier 後に eslint --fix を行う

[eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier)  
eslint のルールとして prettier の設定を書く

[eslint-config-prettier](https://github.com/prettier/eslint-config-prettier)  
eslint から prettier と被っている設定を無効化する

+++

**方法 1**  
prettier-eslint + eslint-config-prettier  
（私はこっち派）

**方法 2**  
eslint-plugin-prettier + eslint-config-prettier

+++

tslint もまったく同じことができる  
（ただし公式が出しているライブラリではない）

[prettier-tslint](https://github.com/azz/prettier-tslint)

[tslint-plugin-prettier](https://github.com/ikatyang/tslint-plugin-prettier)

[tslint-config-prettier](https://github.com/alexjoverm/tslint-config-prettier)

+++

ちなみに json や markdown も整形可

+++

最近 [ver1.0.0 がリリース](https://prettier.io/blog/2018/01/10/1.10.0.html#support-for-vue-single-file-components-3563-by-vjeux)され  
vue の単一ファイルにも対応した

+++

チーム開発時は precommit で発動させると Good  
コードレビューも本質的な部分に集中できる

「ここのインデントが･･･」とか言いたくない
