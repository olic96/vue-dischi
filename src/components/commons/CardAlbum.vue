<template>
  <div class="album">
      <img :src="album.poster" :alt="album.author">
      <h3>{{album.title}}</h3>
      <h5><small>{{album.author}}</small></h5>
      <h5><small>{{album.year}}</small></h5>
  </div>
</template>

<script>
export default {
    name:'CardAlbum',
    props: {
        album: Object,
    }
}
</script>

<style lang="scss" scoped>
    .album{
        text-align: center;
        background-color: #2e3a46;
        margin: 1.25rem;

    img {
        max-width: 100%;
        margin-top: 0.625rem;
        margin-bottom: 0.3125rem;
    }

    h3 {
        color: #fff;
    }

    h5 {
        color: #d3d3d3;
    }
}
</style>