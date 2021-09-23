<template>
  <div>
    {{ title }}
    <button @click="childMethods">プッシュ</button>
  </div>
</template>

<script>
export default {
  name: 'PropsTest',
  props: {
    title: {
      type: String
    },
  },
  methods: {
    childMethods() {
      this.$emit('costom-event', '子から親だーーー！')
    },
  }
}
</script>

<style>

</style>