<template>
  <main>
    <div class="container">
        <MainSelect @select="filterGenre"/>
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
import MainSelect from './MainSelect.vue';
export default {
    components: {
       MainCards,
       MainSelect,
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
}

 
</style>