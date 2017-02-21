<template lang="html">
  <section id="about">
    <img src="http://aurelien-loyer.fr/wp-content/themes/aurelienloyer-fr/img/iceberg.png" class="iceberg">
    <img src="http://aurelien-loyer.fr/wp-content/themes/aurelienloyer-fr/img/boat.png" class="boat">

    <div class="col-xs-12 col-sm-4 photo">
      <img class="trans05 to animate" src="http://aurelien-loyer.fr/wp-content/themes/aurelienloyer-fr/img/moi_picto.png">
    </div>
    <div class="col-xs-12 col-sm-8 bio">
      <h2 class="trans05 to animate">{{about_name}}</h2>
      <br>
      <h3 class="trans05 to animate">{{about_work}}</h3>
      <p class="trans05 to animate">
        {{about_descritpion}}
      </p>
    </div>

    <div class="hover">
      <h3 class="about_more">Pour en savoir plus sur moi, sur mon parcours, n‘hésitez pas à télécharger mon curiculum vitae</h3><br>
      <a target="_blank" href="#url de mon cv....">
        <h3 class="border trans05">TELECHARGER MON CV</h3><img class="save_picto trans05" src="http://aurelien-loyer.fr/wp-content/themes/aurelienloyer-fr/img/save_picto.png">
      </a>
    </div>
  </section>
</template>

<script>
export default {
  name: 'about',
  data(){
    return {
      about_name: "Aurélien Loyer",
      about_work: "Web Consultant @ Zenika",
      about_descritpion: "Consultant Web chez Zenika Lille depuis novembre 2015. J’ai pu m’expérimenter dans le milieu du développement grâce à de nombreux projets chez des clients, à des projets personnels et associatifs ainsi qu'avec des stages effectués pendant mes années d'études @ Supinfo. Je m’intéresse beaucoup aux technologies du WEB et tout ce qui lui appartient. Si vous pensez que je peux vous aider, n'hésitez plus… <br>Je serai ravi de travailler avec vous !"
    }
  },
}

//http://aurelien-loyer.fr/wp-json/wp/v2/about/5
</script>

<style lang="scss">
#about {
  width: 100%;
  height: auto;
  background-color: #4A8CC6;
  position: relative;
  overflow: hidden;
  padding: 4% 0px;
  .iceberg {
    position: absolute;
    margin-left: 45%;
    z-index: 2;
    width: 10%;
    top: -500px;
  }
  .boat {
    position: absolute;
    margin-left: -200px;
    z-index: 2;
    overflow: hidden;
    top: 100%;
    margin-top: -14px;
  }
  .photo {
    text-align: right;
    height: 100%;
    img {
      width: 50%;
      border-left: solid 2px #073F71;
      padding-left: 15%;
    }
  }
  .bio {
    height: 100%;
    h2 {
      font-weight: lighter;
    }
    h3 {
      font-weight: lighter;
      color: #073F71;
    }
    p {
      color: white;
      font-size: 14px;
      max-width: 75%;
      text-align: justify;
      margin-top: 30px;
    }
  }
  .hover {
    display: block;
    width: 100%;
    text-align: center;
    margin-bottom: 50px;
    .about_more {
      font-size: 14px;
      margin-top: 50px;
      width: 100%;
    }
    .border {
      border: solid 3px white;
      padding: 5px 20px;
      margin-top: 1%;
      height: 42px;
    }
    .save_picto {
      height: 48px;
      margin-top: -4px;
      margin-left: 30px;
    }
    a:hover .save_picto {
      margin-top: 5px;
    }
  }
}

@media all and (max-width: 768px) {
  #about {
    .photo {
      img {
        width: 70%;
        border-left: none;
        padding-left: 0%;
        margin: auto;
      }
      text-align: center;
    }
    .bio p {
      max-width: 100%;
    }
    .hover .border {
      border: solid 3px white;
      padding: 5px 20px;
      margin-top: 1%;
      height: auto;
      font-size: 12px;
    }
  }
}
</style>
