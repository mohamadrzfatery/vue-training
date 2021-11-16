<template>
  <events-child @onSuccess="onSuccess"></events-child>
</template>

<script>
export default {
  methods: {
    onSuccess(param) {
      console.log('success', param)
    },
  },
}
</script>

<style></style>
