<template>
    <header id="menu">
        <span id="logo">
            <router-link to="/">Logo</router-link>
        </span>
        <ul options>
            <li>
                <router-link to="/">Home</router-link>
            </li>
            <li>
                <router-link to="/projects">Projetos</router-link></li>
            <li>
                <router-link to="/about">About</router-link>
            </li>
        </ul>  
       <button>
            <img src="https://luzdigi.com.br/img/menu.png" alt="">
        </button>

    </header>
</template>

<script>
    export default{
        name: "Navigation"
    }
</script>

<style  scoped>

    #menu{
        display: flex;
        width: 100%;
        height: 50px;
        background-color: #222;
        color: #ccc;
        justify-content: space-between;
        align-items: center;
        padding: 0 15px;
    }

    ul{
        list-style: none;
        display: flex;
        justify-content: space-around;
        width: 40%;
      
    }



    button{
        height: 80%;
        background-color: #333;
        border: 0 none;
        border-radius: 10px;
        margin-right: 10px;
        width: max-content;
        padding: 10px;
        cursor: pointer;
        display: none;
        transition: .5s;
    }

    button:hover{
        background-color: #444;
    }

    img{
        width: 20px;
        margin: auto;
    }

    @media (max-width: 700px), (orientation:portrait) { 

     [options]{
        display: none;
     }
     button{
        display: block;
     }

    }


</style>