<template>

  <h1> Films:</h1>
  <h4> suite a un soucis d'api il y aura des films a la place des cocktails. </h4>
  <h3>{{cocktails.title}}</h3>
  <img :src="cocktails.poster" class="rounded img-thumbnail">

</template>

<script>
import axios from 'axios';

export default {
  name: 'Cocktails',
  data() {
    return {
      cocktails: null,
    };
  },
  created: function() {

    axios
      .get('https://imdb-internet-movie-database-unofficial.p.rapidapi.com/film/tt1375666', { headers: {
        'x-rapidapi-key': '5ee4b09894mshb2a3ba1fd076540p1358c3jsnbe47eb0a4c5b',
        'x-rapidapi-host': 'imdb-internet-movie-database-unofficial.p.rapidapi.com' }
  })
      .then(res => {
        this.cocktails = res.data;
        console.log(res.data);
      })
  }
}
</script>

<style>
  h3 {
    margin-bottom: 5%;
  }
</style>
