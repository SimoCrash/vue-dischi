<template>
  <div class="container-page">
    <div v-if="arrCard" class="card-page row row-cols-5">
        <SongCard
         v-for="cardSong in arrCard" 
         :key="cardSong.title"
         :poster = "cardSong.poster"
         :title = "cardSong.title"
         :author = "cardSong.author"
         :year = "cardSong.year"
         >{{ cardSong.title }}
        </SongCard>
    </div>
    <div v-else><h1>LOADING...</h1></div>
  </div>
</template>

<script>
import axios from 'axios';
import SongCard from '@/components/SongCard.vue';
export default {
    name: 'MainPage',
    components: {
        SongCard,
    },
    data() {
        return {
            arrCard: null,
        };
    },
    created(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(axiosResponse => {
            this.arrCard = axiosResponse.data.response;
        })
    },
}
</script>

<style lang="scss" scoped>
    .container-page {
        background-color: #1E2D3B;
    }
    .card-page {
        max-width: 70%;
        margin: auto;
    }
</style>