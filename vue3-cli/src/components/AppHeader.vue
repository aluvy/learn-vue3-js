<template>
  <div>
    <h1>{{ appTitle }}</h1>
    <button type="button" @click="changeTitle">change</button>
  </div>
</template>

<script>
export default {
  props: {
    appTitle: String
  },
  methods: {
    changeTitle() {
      this.$emit('changeTitle');
    }
  }
}
</script>
