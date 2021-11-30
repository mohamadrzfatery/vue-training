<template>
  <div>
    <home-header></home-header>
    <home-counter :defaultInitialValue="10" />
    <button @click="initial++">Update prop ({{ initial }})</button>
    <nuxt-link :to="{ name: 'nuxt-middleware' }">nuxt middleware</nuxt-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      initial: 4,
    }
  },
}
</script>

<style lang="sass" scoped></style>
