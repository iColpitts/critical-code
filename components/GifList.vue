<template>
    <div>
        <h1>GIF HAPPINESS!</h1>
        <div v-for="gif in gifs" :key="gif.id">
            <h2>{{gif.url}}</h2>
            <img src="https://giphy.com/gifs/cat-smoke-smoking-3o6Zt481isNVuQI1l6" crossorigin="anonymous">
        </div>
    </div>
</template>

<script>
    export default {
        props: ['gifs'],
    }
</script>

<style scoped>
.gif {
    display: flex;
    align-content: space-between;
    
}
h1 {
    background-color: plum;
}
</style>