<script>
export default{
    name:'AppCarditems',
  data(){
    return{
      

    }
  },
  //  le props possono essere definite come un modo che permette di comunicare tra genitore e figlio
  props:{
    card: Object,
  }
}

</script>

<template>
  <li id="card">
    <!-- abbiamo ricercato dinamicamente gli elementi -->
    <img :src="card.card_images[0].image_url_small" :alt="card.name">
    <strong>{{ card.name }}</strong>
    <span>{{ card.archetype }}</span>

  </li>
 
</template>

<style lang="scss">
@use '../components/styles/variables.scss' as *;
#card{
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #D48F38;
  width: calc(100% / 6 - $gap / 6 * 5);
  padding: 8px;
  
  img{
    width: 100%;
    margin-bottom: 8px;
  }
  strong{
    text-align: center;
    margin-bottom: 15px;
  }
  span{
    color: #2C1E0A;
    
  }
}

</style>
