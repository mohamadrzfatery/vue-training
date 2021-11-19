<template>
  <div>
    <h1>search-todo</h1>
    <input type="text" :value="title" @input="onInput" />
    <p v-if="loading">loading...</p>
    <ul v-else>
      <li v-for="item in list" :key="item.id">
        {{ item.title }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  fetch() {
    // return this.$axios
    //   .$get('https://jsonplaceholder.typicode.com/todos', {
    //     params: {
    //       title_like: this.title,
    //     },
    //   })
    //   .then((response) => {
    //     this.list = response
    //   })
    //   .catch((e) => {        // dar seacrh age sari type konim dochar moshkel mishe pas to function mizanim
    //     console.log(e)
    //   })
    return this.service()
  },
  data() {
    return {
      title: '',
      list: [],
      loading: true, // chon az fetchPending nemitonim inja estefade koinm ino zadim
    }
  },
  methods: {
    service() {
      this.loading = true
      return this.$axios
        .$get('https://jsonplaceholder.typicode.com/todos', {
          params: {
            title_like: this.title,
          },
        })
        .then((response) => {
          this.loading = false
          this.list = response
        })
        .catch((e) => {
          this.loading = false
          console.log(e)
        })
    },
    onInput(e) {
      this.title = e.target.value
      this.service()
    },
  },
}
</script>

<style></style>
