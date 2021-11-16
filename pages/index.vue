<template>
  <div>
    <home-header></home-header>
    <home-counter :initial-counter="initial" />
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
