<template lang="html">
  <section id="home">
        <img src="src/assets/earth.png" class="earth">
        <v-stars></v-stars>
        <v-scroll class="mouse_down"></v-scroll>
        <div class="containt">
            <h2 class="border trans05" v-bind:class="{ animate: isLoading }">{{about_work}}</h2><br>
        </div>
    </section>
</template>

<script>

import Scroll from './home/Scroll.vue'
import Stars from './home/Stars.vue'

export default {
  name: 'home',
  data(){
    return {
      isLoading : true,
      about_name: '',
      about_work: '',
      about_descritpion: ''
    }
  },
  components: {
    'v-scroll': Scroll,
    'v-stars': Stars,
  },
  created(){
    let about_url = 'http://wp.aurelien-loyer.fr/wp-json/wp/v2/about/5'

    this.$http.get(about_url).then(response => {
      if(response.body.acf){
        this.about_name = response.body.acf.about_name
        this.about_work = response.body.acf.about_work
        this.about_descritpion = response.body.acf.about_descritpion
        this.isLoading = false;
      }
    })
  },
}
</script>

<style lang="scss">

$break-small: 320px;
$break-large: 1200px;

#home {
  transition: all 0s;
  background-color: #231f20;
  overflow: hidden;
  background-image: url("/src/assets/stars.png");
  width: 100%;
  background-size: cover;
  background-repeat: no-repeat;
  margin: 0;
  padding: 0;
  height: 100vh;
  width: 100%;
  color: white;
  position: relative;
  z-index: 1;

  .border {
    border: solid 3px white;
    padding: 5px 20px;
  }

  h2:first-child {
    margin-top: 30vh;
    margin-bottom: 5%;
    font-size: 25px;
    padding: 8px 35px;
    font-weight: 300;

    @media screen and (max-width: $break-small) {
      margin-left: 20px;
      margin-right: 20px;
    }
  }

  .earth {
    position: absolute;
    margin-left: 42.5%;
    z-index: 2;
    margin-top: 45vh;
    width: 15%;

    @media screen and (max-width: $break-small) {
      margin-top: 55vh;
    }
  }
  .mouse_down {
    position: absolute;
    width: 3%;
    margin-left: 49%;
    bottom: 10px;
    z-index: 1;
  }
  .containt {
    height: 100%;
    width: 100%;
    text-align: center;
  }
}

@media all and (max-width: 768px) {
  #home {
    .earth {
      position: absolute;
      margin-left: 30%;
      z-index: 2;
      //margin-top: 50%;
      width: 40%;
    }
    .mouse_down {
      position: absolute;
      width: 10%;
      margin-left: 45%;
      bottom: 10px;
      z-index: 1;
    }
  }
}
</style>
