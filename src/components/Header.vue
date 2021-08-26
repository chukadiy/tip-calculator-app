<template>

    <header>
        <h1> {{title}} </h1>
    </header>

</template>

<script>

export default {
    name: 'Header',
    props: {
        title: String,
    }, 
    
}
</script>

<style scoped>

header { 
    display:flex;
    justify-content:center;
    align-items: center;
    padding-top: 100px ;
    margin-bottom: 80px; 
    color: hsl(183, 100%, 15%);
    /*border: 1px solid black;*/
    }

h1 {
    width: 50px;
    /*border: 1px solid black;*/
    letter-spacing: 4px;
    font-weight: 700;
    font-size: 20px;
}

</style>