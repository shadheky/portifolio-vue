<template>
  <div class="about">
    <h1>Habilidades</h1>
    <div id="stack-container">
       <span id="stack">
          <div query-value="HTML" @click="loadTechnologyDescription($event,'HTML')"><img class="stack-icon" src="img/HTML.png" alt=""></div>
          <div query-value="CSS"  @click="loadTechnologyDescription($event,'CSS')" ><img class="stack-icon" src="img/CSS.png" alt=""></div>
          <div query-value="JavaScript"  @click="loadTechnologyDescription($event,'JavaScript')"><img class="stack-icon" src="img/JavaScript.webp" alt=""></div>
          <div query-value="VueJS"  @click="loadTechnologyDescription($event,'VueJS')"><img class="stack-icon" src="img/Vue.png" alt=""></div>
          <div query-value="Java"  @click="loadTechnologyDescription($event,'Java')"><img class="stack-icon" src="img/Java.png" alt=""></div>
          <div query-value="Spring"  @click="loadTechnologyDescription($event,'Spring Framework')"><img class="stack-icon" src="img/Spring.png" alt=""></div>
          <div query-value="Maven"  @click="loadTechnologyDescription($event,'Maven')"><img class="stack-icon" src="img/Maven.png" alt=""></div>
          <div query-value="MongoDB"  @click="loadTechnologyDescription($event,'MongoDB')"><img class="stack-icon" src="img/MongoDB.png" alt=""></div>
          <div query-value="HTML"  @click="loadTechnologyDescription($event,'PostgreSQL')"><img class="stack-icon" src="img/Postgree.png" alt=""></div>

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
        async loadTechnologyDescription(event, technologyName){
          const req = await fetch(this.baseURL + `/technologys/name/${technologyName}`);

          const resJSON = await req.json();

          ( event.target.tagName === 'IMG')? this.addIconBgColor(event.target.parentElement): this.addIconBgColor(event.target)
          this.technologyDescription = `/*${resJSON.shortDescription}*/`;
        },
        addIconBgColor(element){
          this.removeAllBgIconColor();
          element.classList.add("bg-change");
        },
        removeAllBgIconColor(){
          document.querySelectorAll('.bg-change').forEach( e => e.classList.remove('bg-change'))
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
    padding: 20px;
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
    
    border-radius: 5px;
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

    display: flex;
    justify-content: center;
    align-items: center;
    padding: 10px;
    box-sizing: border-box;
    border-radius: 8px;

    width: max-content;

  }
  
  div [query-value]:hover{

    background-color: #ccc;
    cursor: pointer;
  }

  .bg-change{
    background-color: #ccc;
  }

  @media (max-width:700px){
    #stack-container{
      flex-direction: column;
      width: 90%;
    }

    #technology-description{
      width: 100%;
    }
  
  }

  
</style>