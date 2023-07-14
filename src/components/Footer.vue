<template>
    <footer id="footer">
        <span id="logo">
           Logo
        </span>
  
    </footer>
</template>

<script>
    export default{
        name: "Footer"
    }
</script>

<style  scoped>

  

    #footer{
        display: flex;
        width: 100%;
        height: 50px;
        background-color: #222;
        color: #ccc;
        justify-content: space-between;
        align-items: center;  
    }

    ul{
        list-style: none;
        display: flex;
        justify-content: space-around;
        width: 40%;
      
    }

    #logo{
        margin: 0 20px;
    }



</style>