<template>
    <div>
        <select  id="filter" v-model="search" >
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
                    'alive',
                    'dead',
                    'unknown'
                ],
                search: '',
            }
        },
        props:{

        }
    }
</script>

<style lang="scss" scoped>
    div{
        width: 1170px;
        margin: 20px auto;
        #filter{
            padding: 1rem 2rem;
            border-radius: 5px;
            font-size: 20px;
        }
    }
</style>