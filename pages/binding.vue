<template>
  <div>
    <h1>class and style binding</h1>
    <div :class="[{ active: isActive }, 'b']" @click="toggle" class="binding">
      binding
    </div>
    <div :style="{ color: 'yellow' }">style binding</div>
    {{ isActive.toString() }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
    }
  },
  methods: {
    toggle() {
      this.isActive = !this.isActive
    },
  },
}
</script>

<style scoped>
.binding {
  width: 200px;
  height: 200px;
  background-color: rebeccapurple;
}
.active {
  background-color: royalblue;
}
</style>
