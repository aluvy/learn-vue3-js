# Vue3의 코드 작성 방식

## 옵션 API
```html
<div id="app">{{ message }}</div>

<script>
Vue.createApp({
  data() {
    return {
      message: 'hi'
    }
  }
}).mounte('#app');
</script>
```

## Composition API
```html
<div id="app">{{ message }}</div>

<script>
Vue.createApp({
  setup() {
    const message = ref('hi');

    return {
      message
    }
  }
}).mounte('#app');
</script>
```
