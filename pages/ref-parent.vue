<template>
  <div>
    <h1>ref-parent</h1>
    <ref-parent-child ref="myRef"></ref-parent-child>
    <button @click="resetChild">reset from parent</button>
    <hr />
    <ref-parent-child ref="myRef"></ref-parent-child>
    <div>
      <span>parentCount : {{ parentCount }}</span>
    </div>
  </div>
</template>

<script>
import RefParentChild from '~/components/RefParentChild.vue'
export default {
  components: { RefParentChild },
  data() {
    return {
      parentCount: 0,
    }
  },
  //   beforeMount() {
  //     this.$refs.myRef.reset() // in harekat eshtebast va baes error mishe nabayad to beforemount ino bezani
  //   },
  methods: {
    resetChild() {
      this.$refs.myRef.reset()
    },
  },
}
</script>

<style></style>
