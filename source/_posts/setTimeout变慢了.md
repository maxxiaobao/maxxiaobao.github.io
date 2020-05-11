---
title: setTimeout 延时
date: 2020-5-10 20:03
---

`setTimeout` 是 window 对象的一个方法，可以设置一个定时器，在定时结束后运行一个callback 函数。

```
let timeoutID  = setTimeout(cb [,delay], arg1, arg2,...);
```

我们经常用它来写倒计时，但会出现延时情况

<!-- more -->

### 最小延时 >=4ms

在浏览器中，setTimeout()/setInterval() 的每调用一次定时器的最小间隔是4ms，这通常是由于函数嵌套导致（嵌套层级达到一定深度），或者是由于已经执行的setInterval的回调函数阻塞导致的。

### 未被激活的tabs的定时最小延迟>=1000ms

> To reduce the load (and associated battery usage) from background tabs, timeouts are throttled to firing no more often than once per second (1,000 ms) in inactive tabs.
为了优化后台tab的加载损耗（以及降低耗电量），在未被激活的tab中定时器的最小延时限制为1S(1000ms)。
https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout

所以当页面或者小程序切至后台，setTimeout()/setInterval()便会有延时，在callback里面再次获取时间，处理逻辑。

60S 倒计时：

```
    // 😫
    let l = 60 * 1000;
    const c = setInterval(() => {
      l = l - 1000;
      const restTime = Math.floor(l / 1000);
      this.setData({ countdown: restTime });
      if (restTime <= 0) {
        clearInterval(c);
        this.setData({ countdown: 0 });
      }
    }, 1000);
```

```
    // 😊
    const l = 60 * 1000;
    const beginTime = new Date().getTime();
    const c = setInterval(() => {
      const now = new Date().getTime();
      const spendTime = now - beginTime;
      const restTime = Math.floor((l - spendTime) / 1000);
      this.setData({ countdown: restTime });
      if (restTime <= 0) {
        clearInterval(c);
        this.setData({ countdown: 0 });
      }
    }, 1000);
```

