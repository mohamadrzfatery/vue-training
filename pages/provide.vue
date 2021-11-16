<template>
  <div>
    <provide-child></provide-child>
    <button @click="count++">plus</button>
    <p>root : {{ count }}</p>
  </div>
</template>

<script>
import ProvideChild from '~/components/ProvideChild.vue'
export default {
  components: { ProvideChild },
  provide() {
    return {
      count: this.count,
    }
  },
  data() {
    return {
      count: 0,
    }
  },
}
</script>

<style></style>
