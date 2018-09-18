<template lang="html">
  <section id="about" class="trans05">
    <div class="col-xs-12 col-sm-4 photo">
      <img class="trans05" v-bind:class="{ animate: isLoading }" src="src/assets/moi_picto.png">
    </div>
    <div class="col-xs-12 col-sm-8 bio">
      <h2 class="trans05" v-bind:class="{ animate: isLoading }">{{about_name}}</h2>
      <br>
      <h3 class="trans05" v-bind:class="{ animate: isLoading }">{{about_work}}</h3>
      <p class="trans05" v-bind:class="{ animate: isLoading }">{{decodeHtml(about_descritpion)}}</p>
    </div>
  </section>
</template>

<script>
  export default {
    name: 'about',
    data() {
      return {
        isLoading: true,
        about_name: '',
        about_work: '',
        about_descritpion: '',
        about_photo: ''
      }
    },
    methods: {
      decodeHtml: function (html) {
        var txt = document.createElement("textarea")
        txt.innerHTML = html
        return txt.value
      }
    },
    created() {
      let about_url = 'https://wp.aurelien-loyer.fr/wp-json/wp/v2/about/5'

      this.$http.get(about_url).then(response => {
        if (response.body.acf) {
          this.about_name = response.body.acf.about_name
          this.about_work = response.body.acf.about_work
          this.about_descritpion = response.body.acf.about_descritpion
          this.about_photo = response.body.acf.about_photo
          this.isLoading = false;
        }
      })
    },
  }

//http://aurelien-loyer.fr/wp-json/wp/v2/about/5
</script>

<style lang="scss">
  $break-small: 320px;
  $break-large: 1200px;

  #about {
    width: 100%;
    height: auto;
    background-color: #4A8CC6;
    position: relative;
    overflow: hidden;
    padding: 4% 0px;

    display: flex;
    justify-content: center;

    @media screen and (max-width: $break-small) {
      display: block;
    }

    .photo {
      text-align: right;
      height: 100%;
      width: 300px;
      max-width: 50%;
      margin-right: 10%;

      @media screen and (max-width: $break-small) {
        margin: auto;
        text-align: center;
        max-width: 80%;
      }

      img {
        width: 100%;
        max-width: 220px;
        border-left: solid 3px #073F71;
        padding-left: 15%;
      }
    }
    .bio {
      height: 100%;
      max-width: 50%;

      @media screen and (max-width: $break-small) {
        margin-top: 20px;
        max-width: 80%;
        margin-left: 10%;
      }

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

      display: block;
      text-align: center;

      .photo {
        img {
          width: 70%;
          border-left: none;
          padding-left: 0%;
          margin: auto;
        }
        text-align: center;
        width: 100%;
        margin: 0;
        padding: 0;
        max-width: initial;
      }
      .bio {
        width: 100%;
        max-width: 80%;
        margin: 20px auto;
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
