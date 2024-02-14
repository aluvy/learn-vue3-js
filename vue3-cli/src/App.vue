<template>
  <AppHeader :appTitle="appTitle" @changeTitle="changeTitle"></AppHeader>
  <div>
    {{ msg }}
  </div>
  <button type="button" @click="showAlert">alert</button>
</template>

<script>
import AppHeader from '@/components/AppHeader.vue';

export default {
  components: {
    AppHeader
  },
  data() {
    return {
      msg: 'hi',
      appTitle: '앱 헤더 컴포넌트'
    }
  },
  methods: {
    showAlert() {
      alert('hi')
    },
    changeTitle() {
      this.appTitle = '체인지'
    }
  },
}
</script>

<style>

</style>
