<template>
    <div class="container">
        <form @submit.prevent="getGifs">
            <input type="text" id="search" name="search" v-model="searchTerm">
            <input type="submit" value="Gifs for YOU!">
        </form>
        <GifList v-bind:gifs="gifResults" />
    </div>
</template>

<script>
    import GifList from '@/components/GifList.vue';
    export default {
        components: {
            GifList,
        },
        data() {
            return {
                gifResults: null,
                searchTerm: null
            }
        },
        methods: {
            async getGifs() {
                const results = await this.$axios.$get('/search?api_key=' + process.env.giphyKey + "&q=" + this.searchTerm)
                .then(response => {
                    console.log(response)
                    this.gifResults = response.data
                })
            }
        },
        // async asyncData({ $axios }) {
        //     const ip = await $axios.$get('http://icanhazip.com')
        //     return { ip }
        // }
    }
</script>

<style scoped>

.container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 50px;
}

input {
    padding: 10px;
    margin: 5px;
}

input[type=text] {
    width: 60vw;
}

</style>