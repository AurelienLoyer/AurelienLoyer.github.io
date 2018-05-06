<template lang="html">
  <footer id="footer">
    <a class="trans02" href="https://github.com/T3kstiil3" target="_blank">
      <img src="src/assets/github.png" alt="">
      <br> Github
    </a>
    <a class="trans02" href="https://twitter.com/AurelienLoyer">
      <img src="src/assets/twitter.png" alt="">
      <br> Twitter
    </a>
  </footer>
</template>

<script>
  export default {
    name: 'footer'
  }
</script>

<style lang="scss">
  #footer {
    background: white;
    padding: 4%;
    display: flex;
    justify-content: center;
    a {
      color: #272C2F;
      font-weight: bold;
      text-align: center;
      &:hover {
        transform: scale(0.95);
      }
    }
    img {
      margin: auto 20px;

    }
  }
</style>
