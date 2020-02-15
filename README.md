# syg-vue-interval

## Description
カウントループするだけの Vue Single file component です。

画像の無限フェードインを作りたかったのですが、画像だけでなくブロック要素ごと切り替える必要があったので、汎用性のある本コンポーネントを作成しました。

## Release

- 2020.02.15
  - とりあえず公開

## Usage

### Install

```sh
npm install --save @sygnas/vue-interval-loop
```

### html / JS

```html
<div id="app">
  <vue-interval-loop v-slot:default="slotProps">
    <p v-if="slotProps.now === 0">This is 0.</p>
    <p v-else-if="slotProps.now === 1">This is 1.</p>
    <p v-else>This is other {{slotProps.now}}.</p>
  </vue-interval-loop>
</div>
```

`slotProps.now` を利用して`<transition>`を使えばフェードインなど応用できます。

```javascript
import Vue from 'vue';
import vueIntervalLoop from '@sygnas/vue-interval-loop';

  new Vue({
    el: '#app',
    components: {
      vueIntervalLoop,
    },
  });
```

### Options

`<vue-interval-loop>`の属性。

| 属性 | 初期値 | 説明 |
| --- | --- | --- |
| max | 3 | カウントする最大値。0〜(max - 1)までカウントする |
| start | 0 | カウントの最初の値 |
| delay | 1000 | カウントアップの間隔。ミリ秒 |

## License
MIT