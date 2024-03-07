<script>
import {store} from '../components/store'
export default{
    name:'CardsNumbers',
  data(){
    return{
        store,
      

    }
  },
  
  
}

</script>

<template>

    <!-- inseriamo il valore che ci siamo salvati -->
    <h3>Numero di carte:{{ store.numbersOfCards }}</h3>
  
 
</template>

<style lang="scss">
@use '../components/styles/variables.scss' as *;


</style>