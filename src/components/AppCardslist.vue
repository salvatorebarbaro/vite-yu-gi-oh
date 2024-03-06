<script>
import {store} from '../components/store'
import AppCarditems from '../components/AppCarditems.vue'
export default{
    name:'AppCarditem',
  data(){
    return{
      store,

    }
  },
  components:{
    AppCarditems,
    
  },
  created(){
    
  }
}

</script>

<template>
  <h1>carte</h1>
  <!-- lista -->
  <ul id="card_container">
    <!-- iteriamo dentro all'array di cards che abbiamo inserito in store -->
    <!-- :card="cardcurrent" richiama la props e cosi gli passa le carte  -->
    <AppCarditems v-for="cardcurrent in store.cards" :card="cardcurrent"></AppCarditems>
  </ul>
  
</template>

<style lang="scss">
// stringa per richiamre le variabili
@use '../components/styles/variables.scss' as *;
h1{
  text-transform: uppercase;
}
#card_container{
  display: flex;
  flex-wrap: wrap;
  gap: $gap;
  
}

</style>
