<template>
  <div>
    <props-test :title="addClick" @costom-event="parentMethod"></props-test>
    <form-test v-model="parentValue"></form-test>
    {{ parentValue }}
  </div>
</template>

<script>
import PropsTest from '@/components/PropsTest.vue'
import FormTest from '@/components/FormTest.vue'


export default {
  name: 'Home',
  components: {
    PropsTest,
    FormTest

    
  },
  data() {
    return {
      addClick: 'クリック！！！',
      parentValue: ''
    }
  },
  methods: {
    parentMethod(e) {
      console.log(e);
    }
  }
}
</script>

<style>

</style>