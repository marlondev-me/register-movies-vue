<template>
  <div>
    <b-container class="text-center">
      <h1>Cadastro de Filmes</h1>
    </b-container>
    <div>
    <b-tabs content-class="mt-3">
      <b-tab title="Lista de Filmes" active>
        <list :listdata="movies"/>
      </b-tab>
      <b-tab title="Cadastro">
          <register @registerMovie="getRegisterMovie"/>
      </b-tab>
    </b-tabs>
  </div>
  </div>
</template>

<script>
  import List from '@/views/List';
  import Register from '@/views/Register';

  export default {
    data: () =>{
      return {
        movies: [
          {
            'name': 'Deadpool',
            'note': 5,
          },
          {
            'name': 'Lanterna Verde',
            'note': 1,
          }
        ]
      }
    },
    name: "App",
    components: {
      'list':List,
      'register':Register,
    },

    methods: {
      getRegisterMovie(movie){
        this.movies.push(movie);
        console.log(this.movies);
      }
    }
  };
</script>

<style></style>
