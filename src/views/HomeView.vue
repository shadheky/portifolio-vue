<template>
    <div id="apresentation-container" main-container>
        <div main-wrapper>
          <span id="apresentation">Oi 👋, eu sou o Luiz</span>
      <h1 id="title-apresentation">
        Desenvolvedor Backend
        <span id="icons-container">
      

          <a target="_blank" href="https://github.com/shadheky">
            <i class="fa-brands fa-github icon"></i>
         </a>

         <a target="_blank" href="https://www.linkedin.com/in/luiz-abdoral-5747b3218/">
          <i class="fa-brands fa-linkedin icon"></i>
         </a>


        </span>
      </h1>

      <p id="p-apresentation">Tenho 18 anos, sou desenvolvedor Back-end, com mais de 1 ano de estudo na área.</p>
      <a href="#title-projetos" id="projetos-anchor">

        <img src="img/arrow-down-icon.png" alt="" class="icon arrow-down">

      </a>
        </div>
    </div>
    
</template>

<script>

</script>


<style scoped>

  [main-container]{
    background: linear-gradient(90deg,
     rgb(120, 117, 117) 0%, rgba(243,234,221,1) 49%,
    rgba(243,234,221,1) 98%);
    width: 100%;
    background-attachment: fixed;
    display: flex;
    justify-content: center;
    

  }

  [main-wrapper]{
    display: flex;
    flex-direction: column;
    width: min-content;
    margin: auto;
 
    font-weight: bold;
    margin-top: 6%;
    color: rgb(61, 59, 59);
    box-sizing: border-box;
    flex-wrap: wrap;
  }

  #title-apresentation{
    font-size: clamp(3em, 5vw, 4em);
    margin-bottom: 30px;
    margin-top: 4px;
    
    
  }

  #apresentation{
      font-size: clamp(1em, 1em + 1vw, 1.5em);
  }
  
  #icons-container{
    margin-left: 1%;
    align-content: flex-start;
  }

  .icon{
    margin-right: 10px;
  }

  #icons-container .icon{
      width: 13%;
      cursor: pointer;
  } 

  @media (max-width: 700px), (orientation:portrait) { 

    [main-wrapper]{
      text-align: center;
      height: 90vh;
      margin-top: 20%;
    }

    #title-apresentation{
      text-align: center;
    }
    
}

</style>