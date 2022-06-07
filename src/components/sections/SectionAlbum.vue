<template>
  <section>
      <div class="container">
          <div class="row">
              <CardAlbum v-for="index in album" :key="index"/>
          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios';
import CardAlbum from '../commons/CardAlbum.vue';

export default {
    name: 'SectionAlbum',
    data() {
        return {
           album: [],
        };
    },

    components: {
        CardAlbum,
    }

    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            // handle success
            this.album = response.data;
        })
        .catch((error) => {
            // handle error
            console.log(error);
        });
    }
}
</script>

<style>

</style>