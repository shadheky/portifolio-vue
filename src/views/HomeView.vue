<template>
    <div id="apresentation-container" main-container>
        <div main-wrapper>
          <span id="apresentation">Oi 👋, eu sou o Luiz</span>
      <h1 id="title-apresentation">
        Desenvolvedor Backend
        <span id="icons-container">
      

          <a target="_blank" href="https://github.com/shadheky">
            <img src="https://dsm01pap002files.storage.live.com/y4mCaTOEp62t9CqDy5YJ7biwpOy-rdVqupf9FamCe0JB_gBT3djD9YU-49gS1DHITQhCOFxVZbMT4Z7CuYiKhgErGsH85L_GQ8dApyEH8JzndgNPGafUNsyghGNfhAxf0q-GknqmGr-XRGtctCp0iDOWD96HwOVCT9wENlh1R66x5KpjKQGSlguyI2fwq18vmELhD-qNR8et5xcc_-646K1uGUOPFUN_f0f1hOwTT7hIGM?encodeFailures=1&width=256&height=256" alt="" class="icon">
         </a>

         <a target="_blank" href="https://www.linkedin.com/in/luiz-abdoral-5747b3218/">
           <img src="https://dsm01pap002files.storage.live.com/y4ml1CpyVB3xsUOG6jDp1Bj-WllaZJNLm_6NYl6UdFxvHeg0ZO2rpVXgZ3tsRALqg5GLmisrAkczFgn4cRmgFh20JVUtVgPtjFkUnTxkImZIx-9dmWuB6LydLztj9aKiZl_mXAJZAO4L7r7fDF_qJo77rlmW8PXZshorqWeFoQGmU9o2Ao5xOC9UldA-ILC03DioYUGcRDYhd17Gxk1GyB1nJn3_TNnwiJNLJwA2ijs-Qs?encodeFailures=1&width=256&height=256" alt="" class="icon">
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