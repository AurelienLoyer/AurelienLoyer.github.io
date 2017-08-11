<template lang="html">
  <header>
    <h1>AURÉLIEN<span>/LOYER</span></h1>

    <div class="ico-menu trans05">
      <img data-menu="src/assets/picto-menu.png" data-close="src/assets/picto-close.png" src="src/assets/picto-menu.png">
    </div>

    <div class="menu trans05">
      <ul>
        <li data-section="#home"><a href="#home">HOME</a></li>
        <li data-section="#about"><a href="#about">A PROPOS</a></li>
        <!--<li data-section="#work"><a href="#work">RÉALISATIONS</a></li>-->
        <li data-section="#contact"><a href="#footer">CONTACT</a></li>
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
  user-select: none;
}

.menu-open header {
  height: 100%;
}

header {
  a{
    color: white;
  }
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
