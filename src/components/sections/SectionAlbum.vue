<template>
  <section>
      <div class="container">
          <ChooseGenre @chooseGenre="filterGenre"/>
          <div class="row">
              <CardAlbum class="col-2" v-for="(album, index) in genreFiltered" :key="index" :album="album"/>
          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios';
import CardAlbum from '../commons/CardAlbum.vue';
import ChooseGenre from '../commons/ChooseGenre.vue';

export default {
    name: 'SectionAlbum',
    data() {
        return {
            albums: [],
            genre:'',
        };
    },

    components: {
        CardAlbum,
        ChooseGenre,
    },

    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            // handle success
            this.albums = response.data.response;
            console.log(response.data)
        })
        .catch((error) => {
            // handle error
            console.log(error);
        });
    },

    methods: {
        filterGenre(value) {
            this.genre = value;
        }
    },

    computed: {
        genreFiltered() {
            return this.albums.filter((elm) => elm.genre.includes(this.genre));
        }
    },
}
</script>

<style>
    label {
        color: #fff;
        padding: 0.3125rem;
    }
</style>