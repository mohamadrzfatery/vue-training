<template>
  <div>
    <p>counter is {{ counter }}</p>
    <button @click="counter++">plus</button>
  </div>
</template>

<script>
export default {
  props: {
    initialCounter: {
      type: Number,
      required: true,
    },
  },
  data() {
    return {
      counter: this.initialCounter,
    }
  },
}
</script>

<style></style>
