<template>
<div>
    <h1>Hi  😇</h1>
    <h1>{{input}}</h1>
    <input type="text" v-model="input" placeholder="Search the most handsome...">

    <!-- {{input}} -->
    <ul>
        <!-- <li v-for="(name, index) in names" v-bind:key ='index'> -->
            <li v-for="(name, index) in filteredNames" v-bind:key ='index'>
                
                <!-- {{index}} -->
                <!-- {{name}} -->
                <p class="NS">{{ name }}</p>
        </li>
    </ul>
</div>
    </template>
    <script>
        export default {
            name:'userName',
            data(){
                return {
                    names:[
                        'Parth',
                        'Jose',
                        'Francisco',
                        'Edgar',
                        'Max',
                        'Chencho',
                        'Demian',
                        'Alex',
                        'Citlali',
                        'Luz',
                        'JuanCa'
                    ],
                    input:''
                }
            },computed:{
                filteredNames(){
                    return (this.input !== '' ? this.names.filter(name => name.toLowerCase().includes(this.input.toLowerCase())) : '')
                }
            }
        }
    </script>

    <style scoped>
    input{
        color: rgb(22, 0, 96);
        font-size: 1em;
        background-color: rgba(255, 255, 255, 0.774);
        padding: 1em;
        border-radius: 50px;
        width: 30vw;
        height: 5vh;
    }
    div{
        color: white;
        height: auto;
        width: 40vw;
        background: rgb(2,0,36);
        background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(9,9,121,1) 35%, rgba(0,212,255,1) 100%);;
        border-radius: 10px;
        margin: auto;
        padding: 2em;
        box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75);
        -webkit-box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75);
        -moz-box-shadow: 10px 10px 5px 0px rgba(0,0,0,0.75);
        outline: none;
    }
    ul>li{
        list-style: none;
    }
    .NS{
        background-color: rgba(128, 128, 128, 0.342);
        padding: 0.5em;
        border-radius: 10px;
        box-shadow: 10px 11px 5px -5px rgba(0, 0, 0, 0.45);
        -webkit-box-shadow: 10px 11px 5px -5px rgba(0, 0, 0, 0.45);
        -moz-box-shadow: 10px 11px 5px -5px rgba(0, 0, 0, 0.45);
    }
    </style>
    