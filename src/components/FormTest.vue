<template>
  <div>
    <input :value="value" @input="childValue">
  </div>
</template>

<script>
export default {
  name: 'ChildVmodel',
  props: {
    value: {
      type: String
    }
  },
  methods: {
    childValue(e) {
      this.$emit('input',e.target.value)
    }
  }
}
</script>

<style>

</style>