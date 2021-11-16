<template>
  <events-child @onSuccess="onSuccess"></events-child>
</template>

<script>
export default {
  methods: {
    onSuccess(param) {
      console.log('success', param)
    },
    busHandler(param) {
      console.log('onDelete called', param)
    },
  },
  mounted() {
    this.$nuxt.$on('onDelete', this.busHandler)
  },
  beforeDestroy() {
    this.$nuxt.$off('onDelete', this.busHandler)
  },
}
</script>

<style></style>
