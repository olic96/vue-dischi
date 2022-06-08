<template>
  <div>
    <label for="genre">Choose a genre:</label>
        <select name="genre" id="genre" v-model="selectGenre" @change="$emit('chooseGenre', selectGenre)">
            <option selectGenre="rock">Rock</option>
            <option selectGenre="pop">Pop</option>
            <option selectGenre="metal">Metal</option>
            <option selectGenre="jazz">Jazz</option>
        </select>
  </div>
</template>

<script>
export default {
    name:'ChooseGenre',
}
</script>

<style>

</style>