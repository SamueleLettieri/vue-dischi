<template>
  <main>
    <div class="container">
        <div class="ms_box p-5">
<!--             <div class="card ms_w">
                <img src="" class="card-img-top" alt="">
                <div class="card-body">
                    <p class="card-text"></p>
                </div>
            </div> -->
        </div>
    </div>
  </main>
</template>

<script>
export default {
    data: function() {
        return{
            SpotifyInfo: [],
        }
    },

    methods:{
        getCardsSpotify(){
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((result) => {
                consol.log(result.data.results);
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
   height: 900px;
}

.ms_box{
    display: flex;
    flex-wrap: wrap;
    width: calc((100% / 5) );
}

.ms_w{
    width: 18rem;
}
 
</style>