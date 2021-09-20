<template>
  <div>
    {{ title }}
    <button @click="childMethods">ボタン</button>
  </div>
</template>

<script>
export default {
  name: 'PropsTest',
  props: {
    title: {
      type: String
    }
  },
  methods: {
    childMethods() {
      this.$emit('costom-event', 'おりゃ〜')
    }
  }
}
</script>

<style>

</style>