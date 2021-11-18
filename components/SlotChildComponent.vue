<template>
  <div>
    <h1>dialog</h1>
    <div class="bg-grey">
      <slot></slot>
    </div>
    <slot name="actionButtons" param1="param1"></slot>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.bg-grey {
  background-color: grey;
}
</style>
