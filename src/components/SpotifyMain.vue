<template>
  <main>
    <div class="container">
        <div class="d-flex justify-content-center">
            <MainSelectGender @select="filterGenre"/>
            <MainSelectArtists @select="filterAuthor"/>
        </div>
        <div class="ms_box p-5">
            <MainCards v-for="(card, index) in albumGenre" :key="index"
              :card="card"
            />

        </div>
    </div>
  </main> 
</template>

<script>
import axios from "axios"; 
import MainCards from './MainCards.vue';
import MainSelectGender from './MainSelectGender.vue';
import MainSelectArtists from './MainSelectArtists.vue';
export default {
    components: {
       MainCards,
       MainSelectGender,
       MainSelectArtists,
    },

    data: function() {
        return{
            SpotifyInfo: [],
            albumGenre: [],
        }
    },

    methods:{
        filterGenre(gender) {
            this.albumGenre = [...this.SpotifyInfo].filter((card) => card.genre.includes(gender) );
            console.log(this.albumGenre);
        },

        filterAuthor(author) {
            this.albumGenre = [...this.SpotifyInfo].filter((card) => card.author.includes(author) );
            console.log(this.albumGenre);
        },

        getCardsSpotify(){
          axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((result) => {
                this.SpotifyInfo = result.data.response; 
                console.log(this.SpotifyInfo ); 
                this.albumGenre = this.SpotifyInfo 
            })
            .catch((error) => {
                console.log(error);
            })
        }
    },

    created(){
        this.getCardsSpotify();
    }
}
</script>

<style lang="scss">
main{
   background-color: rgb(27, 32, 46);
   min-height: 1200px;
   height: 100%;
}

.ms_box{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

 
</style>