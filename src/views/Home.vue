<template>
  <div>
    <props-test :title="addClick" @costom-event="parentEvent"></props-test>
  </div>
</template>

<script>
// @ is an alias to /src
import PropsTest from '@/components/PropsTest.vue'

export default {
  name: 'Home',
  components: {
    PropsTest
  },
  data() {
    return {
      addClick: 'クリック成功！'
    }
  },
  methods: {
    parentEvent(e) {
      console.log(e);
    }
  }
}
</script>
