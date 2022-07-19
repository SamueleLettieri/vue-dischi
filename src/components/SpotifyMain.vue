<template>
  <main>
    <div class="container">
        <div class="ms_box p-5">
            <MainCards v-for="(card, index) in SpotifyInfo" :key="index"
              :card="card"
            />

        </div>
    </div>
  </main> 
</template>

<script>
import axios from "axios"; 
import MainCards from './MainCards.vue';
export default {
    components: {
       MainCards,
    },

    data: function() {
        return{
            SpotifyInfo: [],
        }
    },

    methods:{
        getCardsSpotify(){
          axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((result) => {
                /* console.log(result.data.response); */
                this.SpotifyInfo = result.data.response;
                console.log(this.SpotifyInfo ); 
            })
            .catch((error) => {
                console.log(error);
            })
        }
    },

    created(){
        this.getCardsSpotify()
    }
}
</script>

<style lang="scss">
main{
   background-color: rgb(27, 32, 46);
   height: 900px;
   height: 100%;
}

.ms_box{
    display: flex;
    flex-wrap: wrap;
}

 
</style>