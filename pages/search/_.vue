<template>
  <div>
    <button @click="pushQuery">push query</button>
    <h1>search</h1>
    <nuxt-link :to="{ name: 'product-slug', params: { slug: 'samsung-s5' } }"
      >go to product</nuxt-link
    >
    <ul>
      <li v-for="(item, index) in getParams" :key="index">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  beforeMount() {
    console.log(this.$route.query)
  },
  methods: {
    // pushQuery() {
    //   this.$router.push({ query: { search_key: 'samsung', brand_id: 1 } })
    // },
    // pushQuery() {
    //   this.$router.replace({ query: { search_key: 'samsung', brand_id: 1 } }) // in baes mishe ke age bekhay dokme aghab ro bezani bargarde do safe ghabl
    // },
  },
  mounted() {
    console.log(this.$route.params)
    // setTimeout(() => {  // navigate
    //   this.$router.push({
    //     name: 'product-slug',
    //     params: { slug: 'samsung-s5' },
    //   })
    // }, 3000)
  },
  computed: {
    getParams() {
      return this.$route.params.pathMatch.split('/')
    },
  },
}
</script>

<style></style>
