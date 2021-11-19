<template>
  <div>
    <h1>nuxt fecth</h1>
    <div v-if="$fetchState.pending">loading...</div>
    <!-- farghesh ba async date ine ke ba fetch mishe to safe khodesh loading gozasht vali ba asynce nemishe va ta mogheii ke data ro az server nagerefte nemire to safe va fetch ro mitoni to component estefade koni vali async nemishe-->
    <p v-else>
      {{ title }}
    </p>
  </div>
</template>

<script>
export default {
  fetch() {
    return this.$axios
      .$get('https://jsonplaceholder.typicode.com/todos/1')
      .then((response) => {
        this.title = response.title
      })
      .catch((e) => {
        console.log(e)
      })
  },
  data() {
    return {
      title: '',
    }
  },
}
</script>

<style></style>
