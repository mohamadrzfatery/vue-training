<template>
  <div>
    <h1>methods</h1>
    getComputedCount {{ getComputedCount }}
    <div @click="UpdateCounter()">
      UpdateCounter {{ count }}

      <div @click.stop="UpdateCounter2()">UpdateCounter2 {{ count2 }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
      count2: 0,
    }
  },
  computed: {
    getComputedCount() {
      return this.count * 2
    },
  },
  methods: {
    UpdateCounter() {
      this.count++
    },
    UpdateCounter2() {
      this.count2++
    },
  },
}
</script>

<style></style>
