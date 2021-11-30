<template>
  <div>
    <h1>validate</h1>
  </div>
</template>

<script>
export default {
  validate({ params, error }) {
    error({ statusCode: 500, message: 'خطایی رخ داده است' })
    return /^\d+$/.test(params.id) // ghable (+) yani age test kone bebine addade ya na
  },
}
</script>

<style></style>
