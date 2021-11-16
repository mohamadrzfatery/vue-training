<template>
  <div>
    <p>counter is {{ counter }}</p>
    <p>initialCounter {{ initialCounter }}</p>
    <button @click="counter++">plus</button>
  </div>
</template>

<script>
export default {
  props: {
    defaultInitialValue: {
      type: Number,
      require: true,
    },
    initialCounter: {
      type: Number,
      default() {
        return this.defaultInitialValue
      },
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
