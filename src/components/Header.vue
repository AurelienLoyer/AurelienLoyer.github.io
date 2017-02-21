<template lang="html">
  <header>
    <h1>AURÉLIEN<span>/LOYER</span></h1>

    <div class="ico-menu trans05">
      <img data-menu="http://aurelien-loyer.fr/wp-content/themes/aurelienloyer-fr/img/picto-menu.png" data-close="http://aurelien-loyer.fr/wp-content/themes/aurelienloyer-fr/img/picto-close.png" src="http://aurelien-loyer.fr/wp-content/themes/aurelienloyer-fr/img/picto-menu.png">
    </div>

    <div class="menu trans05">
      <ul>
        <li data-section="#home">HOME</li>
        <li data-section="#about">A PROPOS</li>
        <li data-section="#work">RÉALISATIONS</li>
        <li data-section="#work">CONTACT</li>
      </ul>
    </div>
  </header>
</template>

<script>
export default {
  name: 'header'
}
</script>

<style lang="scss">
header {
  position: absolute;
  top: 0;
  width: 100%;
  height: 100px;
  z-index: 3;
  padding-top: 2%;
}

.menu-open header {
  height: 100%;
}

header {
  h1 {
    font-weight: bold;
    font-size: 24px;
    float: left;
    margin: 0px 0px 0px 3%;
    color: white;
    span {
      font-weight: lighter;
    }
  }
  .menu {
    font-size: 15px;
    color: white;
    ul {
      float: right;
      display: inline;
      list-style: none;
      margin-right: 3%;
      margin-top: 8px;
      li {
        display: inline;
        list-style: none;
        letter-spacing: 8px;
        cursor: pointer;
        &:after {
          content: " / ";
        }
        &:last-child:after {
          content: "";
        }
      }
    }
  }
  .ico-menu {
    display: none;
    img {
      height: 40px;
      margin-right: 20px;
      cursor: pointer;
    }
  }
}

@media all and (max-width: 768px) {
  header {
    .ico-menu {
      display: block;
      float: right;
      top: 0;
    }
    .menu {
      position: fixed;
      width: 50%;
      left: 200%;
      ul li {
        display: block;
        &:after {
          content: "";
        }
      }
    }
  }
  body.menu-open {
    .menu {
      right: 0 !important;
      left: auto;
    }
    header .ico-menu {
      display: block;
      float: right;
      right: 50%;
      margin-right: -58px;
      top: 0;
      position: fixed;
      z-index: 999;
    }
  }
}
</style>
