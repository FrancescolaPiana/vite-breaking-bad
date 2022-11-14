<template>
    <div>
        <select  id="filter">
            <option value="1">Select category</option>
            <option value="2"></option>
            <option value="3"></option>
            <option value="4"></option>
        </select>
    </div>
</template>

<script>
    export default {
        name: 'Filter'
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