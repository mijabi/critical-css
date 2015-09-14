# critical-css

元になるファイル（index.html）と、
「inline css と 外部 css ファイルを読み込む処理を書き込んで別名で生成」するファイル（result.html）を指定すると、
head タグ内に、1st view で必要な css と、全体の css を非同期で読み込む js を書き込んで（書き換えて）くれる。

wtf (well that's fantastic !)


## 注意

既存の css の記述を、noscript に書き出すぽいが…

- css を読み込む際、パラメータが付いていると、タスクがうまく走らない

```html:index.html
  <link rel="stylesheet" href="css/hoge.css?1">
  // エラーでタスクが完走しない
```

- script タグで書き出される css に関しては放置ぽい

```html:index.html
  <script><!--
    document.write('<link rel="stylesheet" href="css/hogei.css">');
  --></script>
  // これはそのまま書き出され、ここで利用されている css は考慮されない。
```


### 参考

[Smashing Magazine](http://www.smashingmagazine.com/2015/08/understanding-critical-css/)
[grunt-critical](https://github.com/bezoerb/grunt-critical)
