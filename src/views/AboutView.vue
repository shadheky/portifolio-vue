<template>
  <div class="about">
    <h1>Habilidades</h1>
    <div id="stack-container">
       <span id="stack">
          <div query-value="HTML" @click="loadTechnologyDescription('HTML')"><img class="stack-icon" src="img/HTML.png" alt=""></div>
          <div query-value="CSS"  @click="loadTechnologyDescription('CSS')" ><img class="stack-icon" src="img/CSS.png" alt=""></div>
          <div query-value="JavaScript"  @click="loadTechnologyDescription('JavaScript')"><img class="stack-icon" src="img/JavaScript.webp" alt=""></div>
          <div query-value="VueJS"  @click="loadTechnologyDescription('VueJS')"><img class="stack-icon" src="img/Vue.png" alt=""></div>
          <div query-value="Java"  @click="loadTechnologyDescription('Java')"><img class="stack-icon" src="img/Java.png" alt=""></div>
          <div query-value="Spring"  @click="loadTechnologyDescription('Spring Framework')"><img class="stack-icon" src="img/Spring.png" alt=""></div>
          <div query-value="Maven"  @click="loadTechnologyDescription('Maven')"><img class="stack-icon" src="img/Maven.png" alt=""></div>
          <div query-value="MongoDB"  @click="loadTechnologyDescription('MongoDB')"><img class="stack-icon" src="img/MongoDB.png" alt=""></div>
          <div query-value="HTML"  @click="loadTechnologyDescription('PostgreSQL')"><img class="stack-icon" src="img/Postgree.png" alt=""></div>

       </span>
       <span id="technology-description">
          {{technologyDescription}}
       </span>
    </div>
  </div>
</template>

<script>
  export default{
    name:"About",
    data(){
      return{
        technologyDescription:"/* Clique nas tecnologias ao lado para revelar informações */",
        baseURL:"http://localhost:5050"
      }
    },
    methods:{
        async loadTechnologyDescription(technologyName){
          const req = await fetch(this.baseURL + `/technologys/name/${technologyName}`);

          const resJSON = await req.json();

          this.technologyDescription = `/*${resJSON.shortDescription}*/`;
        }
    }

  }

</script>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Source+Code+Pro:wght@500&display=swap');

  .about{
    display: flex;
    flex-direction: column;
    align-items: center;
    
  }

  #stack-container{
    display: flex;
    justify-content: space-around;
    margin-top: 20px;
    background-color: #f0faf5;
    width: 80%;
    padding: 10px;
    border-radius: 10px;
    max-width: 700px;
  }

  #technology-description{
    width: 49%;
    display: flex;
    align-items: flex-start;
    padding: 20px;
    margin-bottom: 20px;
    font-family: 'Source Code Pro', monospace;
  }

  #stack{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    column-gap: 30px;
    row-gap: 20px;
    padding: 20px;
  }

  .stack-icon{
    width: 50px;
    margin-bottom: 10px;
  }

  div [query-value]{

    
    padding: 10px;
    box-sizing: border-box;
    border-radius: 8px;
    transition: .5s;

  }
  
  div [query-value]:hover{

    background-color: #ccc;
    cursor: pointer;
  }

  @media (max-width:700px){
    #stack-container{
      flex-direction: column;
    }

    #technology-description{
      width: 100%;
    }

    div [query-value]:hover{
  
      background-color: inherit;
  
    }
  }

  
</style>