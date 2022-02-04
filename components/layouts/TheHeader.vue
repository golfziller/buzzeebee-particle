<template >
    <div class="header">
        <h4 ><nuxt-link to="/" class="my-name">Pongtorn Kitwimonrattana</nuxt-link></h4>
    </div>
</template>
<script>
export default {
    name: 'TheHeader'
}
</script>
<style >
    div.header {
        background-color: #4c8495;
        color: white !important;
        height: 50px;
        padding: 10px;
    }
    .my-name {
        color: white;
    }
    .my-name:hover {
        color:white; 
        text-decoration:none; 
        cursor:pointer;  
    }
</style>