# webpack-pug

`$ yarn init`  
`$ yarn add -D webpack webpack-cli webpack-dev-server`

由於需要輸出HTML，所以需要安裝html-webpack-plugin

`$ yarn add -D html-webpack-plugin`  

`$ yarn add -D html-loader pug-html-loader`  

`$ yarn add -D gh-pages`

`$ yarn add -D node-sass sass-loader`
`$ yarn add -D css-loader style-loader`
`$ yarn remove extract-text-webpack-plugin` [DEPRECATED]
`$ yarn add -D mini-css-extract-plugin`

## note

[css-loader, style-loader的使用](http://cloverhsc.blogspot.com/2017/06/webpack7-css-loader-style-loader.html)

`CSS-Loader` 幫我們把css file透過`@import`或是url()的方式載入到 Javascript 內，這樣webpack就可以認得css

`Style-Loader` 當我們用了css-loader之後其實在browser那邊並不認得，所以需要一個可以將載入到Javascript內的css內容轉成browser看得懂的css 語法

這裡我們將 sass 編譯的css獨立拆分出來  
`Style-Loader` 由 `MiniCssExtractPlugin.loader` 取代  
PS. [DEPRECATED]extract-text-webpack-plugin ExtractTextPlugin廢止

[在webpack中使用Sass編譯css](https://medium.com/小彥彥的前端五四三/在webpack中使用sass編譯css-f1c5aaa175ad)

webpack.config.js

```js
rules: [
    {
        test: /\.(sass|scss)$/,
        use: ['style-loader', 'css-loader','sass-loader']
    },
]
```

```js
rules: [
    {
        test: /\.(sass|scss)$/,
        use: [MiniCssExtractPlugin.loader, 'css-loader','sass-loader']
    }
]
```

## References

[如果你是常切版的前端工程師，你一定要知道pug!](https://medium.com/@NorthBei/如果你是常切版的前端工程師-你一定要知道pug-8b2cbc0a784c)  
[在webpack中使用Pug產生Html](https://medium.com/小彥彥的前端五四三/在webpack中使用pug產生html-24eb9fec22c7)  
webpack.config.js [html-loader](https://webpack.js.org/loaders/html-loader/)
webpack.config.js [style-loader](https://webpack.js.org/loaders/style-loader/)
[DEPRECATED][extract-text-webpack-plugin](https://github.com/webpack-contrib/extract-text-webpack-plugin)
[mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin)
[如何用Webpack來打包JavaScript、SCSS/CSS、HTML網頁和任意檔案？](https://magiclen.org/webpack/)