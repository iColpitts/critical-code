<template>
    <div>
        <div v-for="gif in gifs" :key="gif.id">
            {{gif.url}}
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
</style>