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
       <button @click="changeCurrentMobileMenuSituation()">
            <img src="https://luzdigi.com.br/img/menu.png" alt="">
        </button>
        <div id="mobile-options" v-show="mobileMenuIsShowded">  
             <ul>
            <li>
                <router-link to="/" @click="changeCurrentMobileMenuSituation()"><Button class="btn-link">Home</Button></router-link>
            </li>
            <li>
                <router-link to="/projects" @click="changeCurrentMobileMenuSituation()"><Button class="btn-link">Projects</Button></router-link></li>
            <li>
                <router-link to="/about" @click="changeCurrentMobileMenuSituation()"><Button class="btn-link">About</Button></router-link>
            </li>
        </ul> 
    </div>
    </header>
</template>

<script>
    export default{
        name: "Navigation",
        data(){
            return{
                mobileMenuIsShowded:false
            }
        },
        methods:{
            changeCurrentMobileMenuSituation(){
                this.mobileMenuIsShowded = !this.mobileMenuIsShowded;
            }
        }
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
        position: relative;
    }

    ul{
        list-style: none;
        display: flex;
        justify-content: space-around;
        width: 40%;
      
    }

    [options] a{
        padding: 10px;
        border-radius: 5px;
    }

    [options] a:hover{
        background-color: #444;
    }

    #mobile-options{
        height: max-content;
        position: fixed;
        top: 50px;
        right: 0px;
        background-color: white;
        color: black; 
        width: 100%;
    
        padding: 4px 20px;
        
    }

    #mobile-options ul{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        width: 100%;
        margin: 0;
        padding: 0;
    }

    .btn-link{
        width: 100%;
      
        background-color: #222;
        color: white;
        font-weight: bold;
        box-sizing: border-box;
        padding: 4px;
        height: 40px;
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