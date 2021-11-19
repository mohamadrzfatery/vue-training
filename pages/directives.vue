<template>
  <div>
    <h1>directives</h1>
    <ul>
      <template v-for="(item, key) in filterList">
        <li :key="key">
          <!-- v-if="item.id !== 1" -->
          <!-- v-show preformance behtari dare chone item ro az bein nemibare faghat display=none mishe-->
          {{ item.productName }}
        </li>
      </template>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: [
        { id: 1, productName: 'samsung-s5' },
        { id: 2, productName: 'samsung-s8' },
        { id: 3, productName: 'samsung-s9' },
      ],
    }
  },
  computed: {
    filterList() {
      return this.list.filter((item) => item.id !== 1) // v-if="item.id !== 1" ino bejaye v-if benevis chon to v-for v-if bezani performance khoob dar nemiad
    },
  },
}
</script>

<style></style>
