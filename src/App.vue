<template>
  <Navigation />
  <router-view id="main-view" :baseURL="baseURL"/>
  <Footer/>
</template>

<script>
  import Navigation from './components/Navigation.vue';
  import Footer from './components/Footer.vue';

  export default{
    name:"App",
    components:{
      Navigation, 
      Footer
    },
    data(){
      return{
        baseURL:"https://projetos-api.onrender.com"
      }
    }
  }

</script>

<style>
      @import url('https://fonts.googleapis.com/css2?family=Maven+Pro:wght@600&display=swap');
      @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&display=swap');

    *{
      margin: 0;
      padding: 0;
      font-family: 'Maven Pro';
      box-sizing: border-box;
    }

    #main-view{
      min-height: 100vh;
    }

    a{
        text-decoration: none;
        color: inherit;
    }

</style>
