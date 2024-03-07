<script>
import {store} from '../components/store'

import CardsNumbers from '../components/CardsNumbers.vue'

export default{
    name:'Appfilter',
  data(){
    return{
      store,

    }
  },
  components:{
    
    CardsNumbers,
   
    
  },
  created(){
    
  }
}

</script>

<template>
    <div id="Container_filter">
        <h3>Filtro:</h3>
        <!-- @change="$emit('filtro') è un evento che ci permette di inviare un valore all'elemento genitore -->
        <!-- v-model="store.filterValue" passo valore selecvt -->
        <select name="archetype_filter" id="archetype_filter"  @change="$emit('filter')" v-model="store.filterValue">
            <!-- v-for="archetipo_corrente in store.archetypes" ciclo all'interno dell' array di oggetti che mi interessa -->
            <option v-for="archetipo_corrente in store.archetypes" :value="archetipo_corrente.archetype_name">{{ archetipo_corrente.archetype_name}}</option>
        </select>

        <CardsNumbers></CardsNumbers>

    </div>
 
  
</template>

<style lang="scss">
// stringa per richiamre le variabili
@use '../components/styles/variables.scss' as *;

#Container_filter{
    display: flex;
    flex-direction: column;
    margin: 20px 0;
    gap: 10px;
    h3{
        text-transform: uppercase;
        font-size: 18px;
        color: rgba(206, 17, 206, 0.831);
    }
    select{
        max-width: 150px;
        padding: 5px;
        text-transform: uppercase;
        text-align: center;
    }
}

</style>