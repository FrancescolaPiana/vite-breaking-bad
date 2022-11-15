<template>
    <div>
        <h1>{{ title }}</h1>
    </div>
</template>

<script>
    export default {
        name: 'Header',
        props: {
            title: String
        }
    }
</script>

<style lang="scss" scoped>
    h1{
        padding: 2rem;
        text-transform: uppercase;
        color: aliceblue;
        letter-spacing: .4rem;
    }
    
    h1::selection{
            background-color: rgba(0, 100, 0, 0); color: rgb(0, 155, 39);
        }
</style>