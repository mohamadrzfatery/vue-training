<template>
  <div>
    <p>event child</p>
    <button @click="submit">submit</button>
  </div>
</template>

<script>
export default {
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
