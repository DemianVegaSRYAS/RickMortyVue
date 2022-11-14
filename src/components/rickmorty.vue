<template>
    <div class="Wrappuno">
        <h1>Rick & Morty Characters</h1>


        <div v-for="character in characters.results" :key="character.id" class="wrappdos">
            <img v-bind:src="character.image" :alt="character.name" srcset="" class="image_wrapp">
            <br>
            <div class="info_wrapp">
                <p>{{character.name}} - {{character.origin.name}}</p> 
                <p>{{character.species}} - {{character.gender}}</p> 
                <p>
                    <span class="green" v-if="character.status == 'Alive'"></span>
                    <span class="red" v-else-if="character.status == 'Dead'"></span>
                    {{character.status}} </p> 
                <p><b> <i>Last location known:</i> </b>  
                    <br>
                    {{character.location.name}}</p> 
                
            </div>
        </div>


        <!-- <div v-for="character in characters.results" :key="character.id">
        {{character.image}}
        <img v-bind:src="character.image" alt="" srcset="">
        </div> -->
    </div>
</template>
<script>
// let character = null
export default{
    name: 'RickAndMorty',
    data(){
        return{
            characters: []
        }
    }, methods:{
        callingAPI (){
            fetch('https://rickandmortyapi.com/api/character').then(res => res.json().then(data =>{
                this.characters = data
            }))
        }
    }, mounted(){
        this.callingAPI()
    }
}
</script>
<style scooped>
h1{
    padding: 2em;
    background-color: white;
}
.Wrappuno{
    background-color: rgb(19, 19, 19);
}
.wrappdos{
    color: white;
    background-color: rgb(54, 54, 54);
    display: inline-flex;
    margin: 5px;
    padding: 1em;
    border-radius: 10px;
    max-height: 200px;
    /* overflow-y: scroll; */
    width: 40vw;
}

div>img{
    margin: 0.5em;
    padding: 0;
    border-radius: 10px;
}
.info_wrapp{
    display: block;
    overflow-y: scroll;
}
.info_wrapp::-webkit-scrollbar {
    display: none;
}
h3{
    text-align: start;
    font-size: 1.5em;
}
span{
    display: inline-block;
}
.green{
    background-color: green;
    width: 15px;
    height: 15px;
    border-radius: 50%;
}
.red{
    background-color: red;
    width: 15px;
    height: 15px;
    border-radius: 50%;
}
i{
    color: rgb(117, 167, 0);
}
</style>