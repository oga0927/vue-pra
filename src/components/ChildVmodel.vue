<template>
  <div>
    <input type="text" v-model="childParam">
  </div>
</template>

<script>
export default {
  name: 'ChildVmodel',
  data() {
    return {
      childValue: ''
    }
  },
  computed: {
    childParam: {
      // getは表示する方
      get() {
        return this.childValue
      },
      // setはセッティングする方
      set(value) {  //valueで入力された値を表示
        this.childValue = value
        this.$emit('child-event', value)
      }
    }
  }
}
</script>

<style>

</style>