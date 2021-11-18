<template>
  <div>
    <h1>slots</h1>
    <slot-child-component>
      <div class="title">dialog content</div>
      <template #actionButtons="{ param1 }">
        <span>{{ param1 }}</span>
        <button class="button1">button1</button>
        <button class="button2">button2</button>
      </template>
    </slot-child-component>
  </div>
</template>

<script>
import SlotChildComponent from '~/components/SlotChildComponent.vue'
export default {
  components: { SlotChildComponent },
}
</script>

<style scoped>
.title {
  color: red;
}
.button1 {
  color: rosybrown;
}
.button2 {
  color: saddlebrown;
}
</style>
