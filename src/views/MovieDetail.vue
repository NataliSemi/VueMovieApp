<template>
        <div class="movie-detail">
            <h2>{{movie.Title}}</h2>
            <p>{{ movie.Rating }}</p>
            <img :src="movie.Poster" alt="Movie Poster" class="featured-img">
            <p>{{ movie.Plot }}</p>
        </div>
</template>

<script>
import { ref, onBeforeMount } from 'vue';
import { useRoute } from 'vue-router';
import env from '@/env.js'

export default {
    setup() {
        const movie = ref({});
        const route = useRoute();

        onBeforeMount(() => {
            fetch(`http://www.omdbapi.com/?apikey=${env.apikey}&i=${route.params.id}&plot=full`)
                .then(response => response.json())
                .then(data => {
                    movie.value = data;
                })
        });

        return {
            movie
        }
    }
}
</script>
<style lang="scss">
.movie-detail {
    padding: 10em;
    flex-wrap: wrap;

    h2{
        color: #fff;
        font-size: 28px;
        font-weight: 600;
        margin-bottom: 16px;
        flex: 1 1 50;
    }

    .featured-img {
        display: block;
        max-width: 200px;
        margin-bottom: 16px;
    }

    p {
        text-align: right;
        color: #FFF;
        font-size: 18px;
        line-height: 1,5;
    }
}

</style>