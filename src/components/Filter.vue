<template>
    <div>
        <select  id="searchStatus" v-model="search" @change="changed">
        <option selected value="">Select category</option>
            <option :value="status" v-for="(status,i) in statusOptions" :key="i">{{status}}</option>
        </select>
    </div>
</template>



<script>
    export default {
        name: 'Filter',
        data() {
            return {
                statusOptions: [
                    'Breaking Bad',
                    'Better Call Saul'
                ],
                search: '',
            }
        },

        methods: {
            changed(){
                this.$emit('filterchar',this.search)
                console.log(this.search);
            }
        },
        // props:{
        //     searchStatus: String
        // }
    }


    // /api/characters?category=Better+Call+Saul


</script>

<style lang="scss" scoped>
    div{
        width: 1150px;
        margin: 20px auto;
        #searchStatus{
            padding: 1rem 2rem;
            border-radius: 5px;
            font-size: 20px;
        }
    }
</style>