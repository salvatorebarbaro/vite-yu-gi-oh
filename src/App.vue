<script>
// importazione di axios per le chiamate apy
import axios from 'axios';
// importo il mio store
import {store} from '../src/components/store.js'

import AppCardslist from './components/AppCardslist.vue'
import loader from './components/loader.vue'
export default{
  data(){
    return{
      store,
      
      

    }
  },
    components:{
      AppCardslist,
      loader,
  },
  created(){
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
    .then(res=>{
      // abbiamo controllato la nostra apy
      console.log(res.data.data)
      // abbiamo associato il nostro array vuoto ai valori della nostra apy
      this.store.cards=res.data.data

    })
  }
}

</script>

<template>
  <div class="container" id="contenitore_generale">
    <loader v-if="! store.cards.length>0"></loader>
    <AppCardslist></AppCardslist>
  </div>
  
</template>

<style lang="scss">
#contenitore_generale{
  position: relative;
}

</style>
