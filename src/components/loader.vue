<script>
export default{
    name:'loader',
  data(){
    return{
      

    }
  },
  
}

</script>

<template>
    <div id="container_loader">
         <span>Caricamento</span>

    </div>
  
</template>

<style lang="scss">
@use '../components/styles/variables.scss' as *;

#container_loader{
    width: 100%;
    height: 100%;
    background-color: black;
    position: absolute;
    top: 0;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    span{
        font-size: 50px;
        text-transform: uppercase;
        animation: growup 2s linear infinite ;
        @keyframes growup{
            0%{
                font-size: 30px;
            }

            20%{font-size: 40px;}
            40%{font-size: 50px;}
            60%{font-size: 50px;}
            80%{font-size: 40px;}
            100%{font-size: 30px;}

        }

    }
}

</style>
