<template>
  <div>
    {{ item.name }}
  </div>
</template>

<script>
export default {
  name: 'ArrayTest',
  props: {
    item: {
      type: Object
    }
  }
}
</script>

<style>

</style>