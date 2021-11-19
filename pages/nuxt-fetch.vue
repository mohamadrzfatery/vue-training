<template>
  <div>
    <h1>nuxt fecth</h1>
    <div v-if="$fetchState.pending">loading...</div>
    <!-- farghesh ba async date ine ke ba fetch mishe to safe khodesh loading gozasht vali ba asynce nemishe va ta mogheii ke data ro az server nagerefte nemire to safe va fetch ro mitoni to component estefade koni vali async nemishe-->
    <p v-else-if="$fetchState.error">
      {{ $fetchState.error.message }}
    </p>
    <p v-else>
      {{ title }}
    </p>
  </div>
</template>

<script>
export default {
  fetch() {
    return this.$axios
      .$get('https://jsonplaceholder.typicode.com/todos/0')
      .then((response) => {
        this.title = response.title
      })
      .catch((e) => {
        const statusCode = e?.response?.status || 500
        const message = e?.response?.statusText || 'oops error'
        // if (process.server) {
        //   this.$nuxt.context.res.statusCode = statusCode         // age mikhay safe error biad
        // }
        // this.$nuxt.error({ statusCode, message })
        throw new Error(`${message} (${statusCode})`) // age mikhay to hamoon safe dar yek khat error ro neshoonet bede va nare besafe error
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
