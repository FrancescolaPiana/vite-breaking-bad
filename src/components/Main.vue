<template>
    <div class="container">

        <div class="card" v-for="(char,idex) in characters" :key="char.id"  >

            <div class="img">
                <img class=" img-fluid " :src="char.img" :alt="char.name">
            </div>

            <div class="name">
                <h1>{{char.name}}</h1>
            </div>

            <div class="category">
                <h2>{{char.category}}</h2>
            </div>
        
            <div class="status">
                <h3>{{char.status}}</h3>
            </div>

        </div>

    </div>
</template>

<script>
    export default {
        name: 'Main',
        props: ['characters']
    }
</script>

<style lang="scss" scoped>
    @use '../styles/partials.scss/variables' as*; 
    .container{
        width: 1170px;
        // height: 1170px;  
        background-color: aliceblue;  
        margin: 0 auto;
        border-radius: 3px;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        .card{
            padding: 10px;
            height: 315px;
            width: 220px;
            display: flex;
            flex-direction: column;
            align-items: center;
            background-color: $darkgrey;
            margin-top: 5px;
            margin-bottom: 5px;
            border-radius: 5px;
            box-shadow: 0px 4px 7px rgba(0, 0, 0, 0.4);
            .img{
                overflow: hidden;
                height: 200px;
                width: 200px;
                img{
                    width: 200px;
                }
            }
            .name{
                margin-top: 10px;
                width: 200px;
                // background-color: rgb(15, 112, 36);
                h1{
                    color: $white;
                    font-size: 1.3rem;
                    white-space: nowrap;
                    overflow: hidden;
                    text-overflow: ellipsis;
                }
            }
            .category{
                margin-top: 10px;
                width: 200px;
                // background-color: rgb(15, 112, 36);
                h2{
                    color: $white;
                    font-size: .9rem;
                    white-space: nowrap;
                    overflow: hidden;
                    text-overflow: ellipsis;
                }
            }
            .status{
                margin-top: 10px;
                width: 200px;
                // background-color: rgb(15, 112, 36);
                h3{
                    color: $white;
                    font-size: .9rem;
                    white-space: nowrap;
                    overflow: hidden;
                    text-overflow: ellipsis;
                }
            }

        }
    }
</style>