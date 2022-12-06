<template>
  <div class="container-page">
    <div v-if="arrCard" class="card-page row row-cols-5 g-5">
        <SongCard
         v-for="(cardSong, index) in filteredSongs" 
         :key="index"
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
    computed: {
        filteredSongs() {
            if (this.selectedValue === 'none') {
                return this.arrCard;
            }
            return this.arrCard.filter((cardSong) => cardSong.genre === this.selectedValue);
        }
    },
    created(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(axiosResponse => {
            console.log(axiosResponse)
            this.arrCard = axiosResponse.data.response;
        })
    },
    props: {
        selectedValue: String,
    }
}
</script>

<style lang="scss" scoped>
    .container-page {
        background-color: #1E2D3B;
    }
    .card-page {
        width: 80%;
        margin: auto;
    }
</style>