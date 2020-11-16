<template>
  <div>
    <b-container>
      <b-row class="justify-content-md-center mt-4">
        <b-col col md="8">
          <b-card 
            header="Registre o filme com nota"
            header-bg-variant="primary"
            header-text-variant="black"
          >
          <b-card-text>
            <b-form @submit="handleSubmit">
              <b-form-group label="Nome do filme: ">
                <b-form-input v-model="name" required>
                </b-form-input>
              </b-form-group>
              <b-form-group label="Nota do filme:">
                <b-form-input v-model="note" required type="number" min=1>
                </b-form-input>
              </b-form-group>
              <b-form-group>
                <b-button type="submit" variant="outline-primary">
                  CADASTRAR
                </b-button>
              </b-form-group>
            </b-form>
          </b-card-text>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
  export default{
    data(){
      return{
        name: '',
        note: '',
      }
    },
    methods: {
      handleSubmit(e){
        e.preventDefault();
        
        let movie = {
          name: this.name,
          note: this.note,
        };
        console.log(movie);

        this.$emit('registerMovie', movie);

        alert('Filme Cadastrado com sucesso!')
        this.name = '';
        this.note = '';
        

      }

    }

  }
 
</script>