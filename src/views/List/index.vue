<template>
  <div>    
    <b-table 
      striped 
      hover
      :fields="fields"
      :items="movies" 
      />
  </div>
</template>
<script>
  import { BTable } from "bootstrap-vue";

  export default{
    props: {
      listdata: {
        type: Array,
        required: true,
        validator: (value) =>{
          if (typeof value === 'undefined')
            return false;
          return true;
        }
      }
    },
    components:{
      BTable
    },
    data(){
      return{
        movies: this.listdata, 
        fields:[
          {
            key: 'name', 
            label: 'Nome:', 
            sortable: true
          },
          {
            key: 'note', 
            label: 'Nota:',
            sortable: true
          }
        ]
      }
    }
  }  

</script>