<template>
  <div>
    <event-child-nested />
    <hr />
    <p>event child</p>
    <button @click="submit">submit</button>
  </div>
</template>

<script>
import EventChildNested from './EventChildNested.vue'
export default {
  components: { EventChildNested },
  methods: {
    submit() {
      setTimeout(() => {
        this.$emit('onSuccess', 'my custom param')
      }, 1000)
    },
  },
}
</script>

<style></style>
