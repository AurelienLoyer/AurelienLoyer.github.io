<template lang="html">
  <section id="home">
        <img src="http://aurelien-loyer.fr/wp-content/themes/aurelienloyer-fr/img/earth.png" class="earth">
        <img src="http://aurelien-loyer.fr/wp-content/themes/aurelienloyer-fr/img/scroll-down.gif" class="mouse_down">
        <div class="containt">
            <h2 class="border">{{about_work}}</h2><br>
        </div>
    </section>
</template>

<script>
export default {
  name: 'home',
  data(){
    return {
      about_work: "Web Consultant @ Zenika"
    }
  },
}
</script>

<style lang="scss">
#home {
  transition: all 0s;
  background-color: #231f20;
  overflow: hidden;
  background-image: url("http://aurelien-loyer.fr/wp-content/themes/aurelienloyer-fr/img/stars.png");
  width: 100%;
  background-size: cover;
  background-repeat: no-repeat;
  margin: 0;
  padding: 0;
  height: 100vh;
  width: 100%;
  color: white;
  position: relative;
  .border {
    border: solid 3px white;
    padding: 5px 20px;
  }
  h2:first-child {
    margin-top: 30vh;
    margin-bottom: 5%;
    font-size: 25px;
    padding: 8px 35px;
  }
  .earth {
    position: absolute;
    margin-left: 42.5%;
    z-index: 2;
    margin-top: 45vh;
    width: 15%;
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
