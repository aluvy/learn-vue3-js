# learn-vue3-js

### Proxy() 기반의 Vue3
```
＊ vue2 - Object.defineProperty() 기반으로 나중에 추가 된 데이터에 대해서 reactivity가 동작하지 않음
＊ vue3 - Proxy() 기반으로 나중에 추가된 데이터에 대해서도 reactivity가 동작함
```

## 문법 변화
### vue2
```javascript
new Vue({
  el: '#app'
});

new Vue({}).$mount('#app');
```

### vue3
```javascript
Vue.createApp({
  data() {
    return {
      message: 'hi'
    }
  }
}).mount('#app');
```
