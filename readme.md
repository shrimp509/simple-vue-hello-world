
# 學習記錄

### Lesson 1：簡單的互動

> 參考：勇者鬥Vue龍系列 的 教學文章 [https://ithelp.ithome.com.tw/articles/10202461](https://ithelp.ithome.com.tw/articles/10202461)

1. 綁定一個 button click event，並更新畫面上的文字 (透過 `v-on:click` 綁定 click event)

```js
<div id="app">
  {{ message }}
  <button v-on:click="getRemoteMessage">Click</button>  // 透過 v-on:click 綁定
</div>

var vue = new Vue({
  data: {
    message: 'init text, it will be covered after clicking button',
  },
  methods: {
    getRemoteMessage() {
      Promise.resolve("Hey, don't click me!")
        .then((res) => {
          this.message = res;
        });
    },
  }
})
```

2. 在 div 外的 button，也能更新 div 內的資料 (透過 vue 變數存取到 div 的值)

```js
<div id="app">
  {{ message }}
</div>
<button onclick="outsideButtonClickEvent">Outside Button</button>  // 透過 onclick 綁定

var vue = new Vue({
  data: {
    message: 'init text, it will be covered after clicking button'
  }
})

function outsideButtonClickEvent() {
  Promise.resolve("Hey, don't click me! - from outside button")
    .then((res) => {
      vue.message = res;  // 透過 vue 變數存取到 message
    });
}
```
