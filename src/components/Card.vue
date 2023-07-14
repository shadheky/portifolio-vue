<template>
  <div id="card" class="card" style="width: 100%;">
  <img class="card-img-top" :src="cardContent.imgSrc" alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">{{cardContent.title}}</h5>
    <p class="card-text">{{cardContent.text}}</p>

  </div>
</div>
</template>


<script>
    export default{
        name:"Card",
        props:{
            cardContent:Object
        },
        data(){
            
        }
    }
</script>


<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Ysabeau+Office:wght@600&display=swap');

    .card{
      margin: 12px;
      max-width: 350px;
      min-height: 200px;
      text-align: center;
      background-color: #fafaf5;
      padding: 4px;
      border-radius: 0px;
    }

    .card-text{
      font-family: 'Ysabeau Office', sans-serif;
      color: black;
      font-size: 1.1em;
    }

    h5{
      color: #1b4079;
    }
</style>