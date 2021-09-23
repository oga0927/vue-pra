<template>
  <div>
    <props-test :title="addClick" @costom-event="parentMethod"></props-test>
    <form-test v-model="parentValue"></form-test>
    <child-vmodel @child-event="parentParam = $event"></child-vmodel>
    {{ parentValue }}
    <input :value="test" @input="test = $event.target.value">
    {{ test }}
    <array-test 
      v-for="member in members"
      :key="member.name"
      :item="member"
    >
    </array-test>
  </div>
</template>

<script>
import PropsTest from '@/components/PropsTest.vue'
import FormTest from '@/components/FormTest.vue'
import ChildVmodel from '@/components/ChildVmodel.vue'
import ArrayTest from '@/components/ArrayTest.vue'


export default {
  name: 'Home',
  components: {
    PropsTest,
    FormTest,
    ChildVmodel,
    ArrayTest
  },
  data() {
    return {
      addClick: 'クリック！！！',
      parentValue: '',
      parentParam: '',
      test: '',
      members: [
        {name: 'ミッキー'},
        {name: 'ミニー'},
        {name: 'ドナルド'},
      ]

    }
  },
  methods: {
    parentMethod(e) {
      console.log(e);
    },
  }
}
</script>

<style>

</style>