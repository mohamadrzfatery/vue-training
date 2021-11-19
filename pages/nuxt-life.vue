<template>
  <div>
    <h1>ssr and nust lifeCycle methods</h1>
    {{ name }}
    {{ title }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'ali',
    }
  },
  async asyncData({ $axios }) {
    const response = await $axios.$get(
      'https://jsonplaceholder.typicode.com/todos/1'
    )
    return { title: response.title }
  },
}
</script>

<style></style>
