<script>
// importazione di axios per le chiamate apy
import axios from 'axios';
// importo il mio store
import {store} from '../src/components/store.js'

import AppCardslist from './components/AppCardslist.vue'
import loader from './components/loader.vue'
import Appfilter from './components/Appfilter.vue'
export default{
  data(){
    return{
      store,
      
      

    }
  },
    components:{
      AppCardslist,
      loader,
      Appfilter,
  },
  created(){
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
    .then(res=>{
      // abbiamo controllato la nostra apy
      console.log('carte',res.data.data)
      // abbiamo associato il nostro array vuoto ai valori della nostra apy
      this.store.cards=res.data.data

    }),
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php?')
    .then(res=>{
      // abbiamo controllato la nostra apy e siamo andati a vedere dove fosse il valore che ci interessava
      console.log('archetipi',res.data)
      // abbiamo associato il nostro array vuoto ai valori della nostra apy che riguarda gli archetipi
      this.store.archetypes= res.data

    })
  },

  methods: {
    filtrocarte(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype='+ this.store.filterValue )
        .then(res=>{
      // abbiamo controllato la nostra apy
      console.log('carte',res.data.data)
      // memorizziamo/aggiorniamo un altra volta le carte in base al archetipo
      this.store.cards=res.data.data
      // salviamo nella variabile il numero di carte che vengono scelte
      this.store.numbersOfCards=res.data.meta.total_rows
      

    })
    }
    
  },
}

</script>

<template>
  <div class="container" id="contenitore_generale">
    <!-- riportiamo il filtro nel contenitore padre cosi da poterlo utilizzare -->
    <Appfilter @filter="filtrocarte"></Appfilter>
    <!-- v-if="! store.cards.length>0" condizione che fa vedere loader se lunghezza è maggiore di 0 non si vede il loader -->
    <loader v-if="! store.cards.length>0"></loader>
    <AppCardslist></AppCardslist>
  </div>
  
</template>

<style lang="scss">
#contenitore_generale{
  position: relative;
}

</style>