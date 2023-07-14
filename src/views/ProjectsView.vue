<template>
    <div class="projects-container">
        <h1>Projetos</h1>
        <div class="card-container">
            <Card v-for="project in cardsContent" :key="project.id" :card-content="project"/>
         
        </div>
    </div>
</template>

<script>
    import Card from '@/components/Card.vue';

    export default{
        name:"ProjetosView",
        components:{
            Card
        },
        data(){
            return{
                cardsContent:[],
                baseUrl:"http://localhost:5050"
            }
        },
        mounted(){
            this.loadProjectsContent();
        },
        methods:{
            async loadProjectsContent(){
                try{
                    const req = await fetch(this.baseUrl+"/projects/author/Luiz");
                const res = await req.json();
                
                this.parseProjectsJsonToCardsContent(Array.from(res));
                }catch(e){
                    console.log(e);
                }
                
            },
            parseProjectsJsonToCardsContent(projectsJson){
                this.cardsContent = projectsJson.map( element => {
                    return {
                        title: element.name,
                        text: element.description,  
                        imgSrc: element.imageURL
                    }
                } )
            }
        }
    }
</script>

<style scoped>
    .projects-container{
      width: 100%;
      display: flex;
      flex-direction: column;
     
      align-items: center;
      margin: 20px 0;
    }

    .card-container{
        display: grid;
        grid-template-columns: repeat( 4, 1fr );
        place-items: center;
        width: 80%;
        column-gap: 20px;
    }




    .card {
        grid-column: span 2;
    }

    .card:nth-last-child(1):nth-child(odd) {
        grid-column: 2 / span 2;
        margin-top: 20px;

    }

    @media(max-width: 700px){
        .card-container{
            grid-template-columns: auto;
        }

        .card {
        grid-column: span 4;
        }
    }
</style>