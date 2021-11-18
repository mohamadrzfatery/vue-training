<template>
  <div>
    <h1>watch</h1>
    <button @click="count++">plus</button>
    <button @click="changeObject">change</button>
    <div>
      {{ myObject }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
      myObject: {
        child: { a: 1 },
      },
    }
  },
  methods: {
    changeObject() {
      this.myObject.child.a++
    },
  },
  watch: {
    count: {
      handler(value, oldvalue) {
        console.log('value', value, 'oldvalue', oldvalue)
      },
      immediate: true,
    },
    myObject: {
      handler(value) {
        console.log('myvalue', value)
      },
      deep: true, // yani taghiraate dakhel object ro neshoon bede
    },
    'myObject.child.a'(value) {
      console.log('value', value)
    },

    // count(value, oldvalue) {
    //   console.log('value', value, 'oldvalue', oldvalue)
    // },
  },
}
</script>

<style></style>
