<template lang="html">
  <section id="dates">

    <h2>Conférences / Speaker</h2>

    <div class="row past">
      <div class="point" v-for="date in past">
        <div class="item">
          {{date.text}}
        </div>
      </div>
    </div>

    <div class="row futur">
      <div class="point" v-for="date in futur">
        <div class="item">
          <span v-if="date.text" v-html="date.text" />
          <img v-if="date.icon" :alt="date.alt" :src="date.icon" />
        </div>
      </div>
    </div>

    <a class="button" target="_blank" href="http://talks.aurelien-loyer.fr/">View all talks</a>

  </section>
</template>

<script>
export default {
  name: "dates",
  data() {
    return {
      past: [
        {
          text: "Devoxx France 2017"
        },
        {
          text: "Devfest Lille 2017"
        },
        {
          text: "Meetup GDG Lille"
        },
        {
          text: "Devoxx France 2018"
        },
        {
          text: "Devfest Lille 2018"
        }
      ],
      futur: [
        {
          text: "Montreal"
        },
        {
          icon: "src/assets/dolorean_w.svg",
          alt: "dolorean"
        },
        {
          text: "Coming soon"
        }
      ]
    };
  }
};
</script>

<style lang="scss">
#dates {
  background: #272c2f;
  padding: 50px 10%;

  .year {
    width: 100%;
    text-align: center;
    margin: 50px 0;
  }

  .button {
    background: white;
    border-radius: 5px;
    padding: 11px 20px;
    text-transform: uppercase;
    text-align: center;
    display: table;
    margin: auto;
  }

  .row {
    height: 2px;
    background: white;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    margin: 50px 0px 120px;

    @media screen and (max-width: 600px) {
      justify-content: space-between;
    }

    .point {
      height: 12px;
      width: 12px;
      background: #282c2f;
      border: 3px solid white;
      border-radius: 100%;

      &.futur img path {
        fill: red;
      }

      .item {
        display: flex;
        justify-content: space-around;
        text-align: center;
        padding-top: 20px;
      }
    }
  }
}
</style>
