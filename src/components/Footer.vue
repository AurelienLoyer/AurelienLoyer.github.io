<template lang="html">
  <footer id="footer">
    <a href="https://github.com/T3kstiil3" target="_blank">
      <img class="trans05" src="src/assets/github.png" alt="">
    </a>
    <a href="https://twitter.com/T3kstiil3">
      <img class="trans05" src="src/assets/twitter.png" alt="">
    </a>
  </footer>
</template>

<script>
export default {
  name: 'footer'
}
</script>

<style lang="scss">

#footer{
  background: white;
  padding: 4%;
  text-align: center;
  img{
    margin: auto 20px;
    &:hover{
      transform: scale(0.9);
    }
  }
}

</style>
