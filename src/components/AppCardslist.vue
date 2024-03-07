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
  <div id="title_container">
    <img src="https://www.logolynx.com/images/logolynx/8a/8a629aa27c090b4ec0d27fe78e63c8f5.jpeg" alt="">
    <h1>Yu-Gi-Ho Api</h1>
  </div>
  
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
#title_container{
  display: flex;
  background-color: white;
  align-items: center;
  gap: 10px;
  h1{
  text-transform: uppercase;
  
  color: black;
}
img{
  width:120px ;
  height: 70px;
}
}

#card_container{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: $gap;
  background-color: grey;
  margin: 0px;
  padding: 15px;
  
}

</style>