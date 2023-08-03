<template>
  <div class="about">
    <h1 class="title">Habilidades</h1>
    <div id="stack-container">
       <span id="stack">
          <div  @click="loadTechnologyDescription($event,'HTML')"><img class="stack-icon" src="img/HTML.png" alt=""></div>
          <div   @click="loadTechnologyDescription($event,'CSS')" ><img class="stack-icon" src="img/CSS.png" alt=""></div>
          <div   @click="loadTechnologyDescription($event,'JavaScript')"><img class="stack-icon" src="img/JavaScript.jpg" alt=""></div>
          <div   @click="loadTechnologyDescription($event,'VueJS')"><img class="stack-icon" src="img/Vue.png" alt=""></div>
          <div   @click="loadTechnologyDescription($event,'Java')"><img class="stack-icon" src="img/Java.png" alt=""></div>
          <div   @click="loadTechnologyDescription($event,'Spring Framework')"><img class="stack-icon" src="img/Spring.png" alt=""></div>
          <div   @click="loadTechnologyDescription($event,'Maven')"><img class="stack-icon" src="img/Maven.png" alt=""></div>
          <div   @click="loadTechnologyDescription($event,'MongoDB')"><img class="stack-icon" src="img/MongoDB.png" alt=""></div>
          <div   @click="loadTechnologyDescription($event,'PostgreSQL')"><img class="stack-icon" src="img/Postgree.png" alt=""></div>

       </span>
       <span id="technology-description">
          <h1 :style="technologyTitleColor">{{technologyTitle}}</h1>
          {{technologyDescription}}
       </span>
    </div>
    <h1 class="title">Minha formação</h1>
    <div class="training">
      <img class="avatar" src="/img/avatar.jpg" alt="">
      <p>
        Estou atualmente cursando o segundo semestre de Análise e Desenvolvimento de Sistemas pela universidade Estácio, todavia desenvolvo minhas capacidades na área de desenvolvimento de software desde 2021. 
      </p>
    </div>
  </div>
</template>

<script>
  export default{
    name:"About",
    props:{
      baseURL:String
    },
    data(){
      return{
        technologyDescription:"/* Clique nas tecnologias ao lado para revelar informações */",
        technologyTitle:"",
        technologyTitleColor: "color: #000",
       
      }
    },
    methods:{
        async loadTechnologyDescription(event, technologyName){
          const req = await fetch(this.baseURL + `/technologys/name/${technologyName}`);
          const technologyResponse = await req.json();

          ( event.target.tagName === 'IMG' )? this.addIconBgColor(event.target.parentElement): this.addIconBgColor(event.target)
          this.showTitle(technologyResponse.name);
          this.changeTitleColor(technologyResponse.mainColorInHex);

         
          this.technologyDescription = `/*${technologyResponse.shortDescription}*/`;
        },
        addIconBgColor(element){
          this.removeAllBgIconColor();
          element.classList.add("bg-change");
        },
        removeAllBgIconColor(){
          document.querySelectorAll('.bg-change').forEach( e => e.classList.remove('bg-change'));
        },
        showTitle(text){
          this.technologyTitle = text;
        },
        changeTitleColor( colorInHex ){
          this.technologyTitleColor = `color:${colorInHex};`;
        }
    }

  }

</script>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Source+Code+Pro:wght@500&display=swap');

  .title{
    margin-top: 5vh;
  }
  .about{
    display: flex;
    flex-direction: column;
    align-items: center;
    
  }

  #stack-container{
    display: flex;
    justify-content: space-around;
    margin-top: 20px;
    background-color: #fbfaff;
    width: 80%;
    padding: 20px;
    border-radius: 10px;
    max-width: 700px;
    border: 0.5px solid #ccc;
  }

  #technology-description{
    width: 49%;
    display: flex;
    flex-direction: column;
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
    place-items: center;
  }

  .stack-icon{
    width: 50px;
    margin-bottom: 10px;
  }

  #stack div{

    display: flex;
    justify-content: center;
    align-items: center;
    padding: 10px;
    box-sizing: border-box;
    border-radius: 8px;

    cursor: pointer;
    width: max-content;

  }
  
  #stack div:hover{

    background-color: #ccc;
  }

  .bg-change{
    background-color: #ccc;
  }

  .training{
    width: 80%;
    background-color: #fbfaff;
    border: 0.5px solid #ccc;
    border-radius: 10px;
    padding: 20px;
    max-width: 700px;
    text-align: center;
    margin: 20px auto;
  }

  .avatar{
    width: 200px;
    border-radius: 100px;
    margin-bottom: 10%;
    border: 1px solid #ccc;
  }

  @media (max-width:700px){
    #stack-container{
      flex-direction: column;
      width: 90%;
    }
    .training{
      width: 90%;
    }

    #technology-description{
      width: 100%;
   
    }
  
  }

  
</style>
