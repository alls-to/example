<!-- App.vue -->
<template>
  <div>
    <PaymentButton :onCompleted="onCompleted" :option="option" :host="host" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import PaymentButton from '@alls-to/vue'



export default defineComponent({
  name: 'App-Demo',
  methods: {},
  components: {
    PaymentButton,
  },

  setup(props) {
    function onCompleted(e: any) {
      console.log('Payment completed!', e)
    }

    const option = {
      customer: '',
      id: 'allsto-demo/product1',
      method: 'crypto,fiat',
    }
    // const host = `https://gateway.alls.to/checkout`
     const host = `http://localhost:3000/checkout`

    return { onCompleted, option, host }
  },

})
</script>

<style>
#app {
  text-align: center;
  margin-top: 60px;
}
</style>
