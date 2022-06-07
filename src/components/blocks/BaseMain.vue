<template>
  <main>
    <SectionAlbum/>
  </main>
</template>

<script>
import SectionAlbum from '../sections/SectionAlbum.vue'
export default {
  components: { SectionAlbum },
    name: 'BaseMain',
}
</script>

<style>
  main {
    background-color: #1e2d3b;
  }
</style>