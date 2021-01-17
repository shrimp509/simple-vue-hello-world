
# 學習記錄

1. 綁定一個 button click event，並更新畫面上的文字

```js
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

* 參考：勇者鬥Vue龍系列 的 教學文章 [https://ithelp.ithome.com.tw/articles/10202461](https://ithelp.ithome.com.tw/articles/10202461)
