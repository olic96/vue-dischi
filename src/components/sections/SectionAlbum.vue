<template>
  <section>
      <div class="container">
          <label for="genre">Choose a genre:</label>
            <select name="genre" id="genre">
                <option value="rock">Rock</option>
                <option value="pop">Pop</option>
                <option value="metal">Metal</option>
                <option value="jazz">Jazz</option>
            </select>
          <div class="row">
              <CardAlbum class="col-2" v-for="(album, index) in albums" :key="index" :album="album"/>
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
           albums: [],
        };
    },

    components: {
        CardAlbum,
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
    }
}
</script>

<style>

</style>