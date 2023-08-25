<template>
    <div class="projects-container">
        <h1 class="text-center">Projetos</h1>
        <div class="card-container container">
           <div class="row justify-content-center">
                <Card class="col-md-6 col-xl-4" v-for="project, in cardsContent" :key="project.id" :card-content="project"/>
           </div>
         
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
        props:{
            baseURL:String
        },

        data(){
            return{
                cardsContent:[],
            }
        },
        mounted(){
            this.loadProjectsContent();
        },
        methods:{
            async loadProjectsContent(){
                try{
                    const req = await fetch(this.baseURL+"/projects/author/Luiz Alberto De Souza Abdoral Lopes");
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
                        imgSrc: element.imageURL,
                        projectUrl: element.projectUrl


                    }
                } 
                )
            }
        }
    }
</script>
