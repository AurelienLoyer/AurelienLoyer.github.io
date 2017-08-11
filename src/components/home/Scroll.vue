<template>
    <div>
        <span class="scroll-icon">
            <span class="scroll-icon__wheel-outer">
                <span class="scroll-icon__wheel-inner"></span>
            </span>
        </span>
    </div>
</template>

<script>
export default {
  name: 'scroll'
}
</script>

<style lang="scss">

.scroll-icon {
  display: block;
  position: relative;
  height: 3em;
  width: 1.5em;
  border: .20em solid #fff;
  border-radius: 1em;
}

@keyframes scroll_effect{
  0%   { transform: translateY(0); }
  25%  { transform: translateY(-0.6em); }
  50%  { transform: translateY(0); }
  75%  { transform: translateY(0.6em); }
  100% { transform: translateY(0); }
}

.scroll-icon__wheel-outer {
  display: block;
  position: absolute;
  left: 50%;
  top: .6em;
  height: 1em;
  width: .4em;
  margin-left: -.2em;
  border-radius: .4em;
  overflow: hidden;
}

.scroll-icon__wheel-inner {
  display: block;
  height: 100%;
  width: 100%;
  border-radius: inherit;
  background: #fff;
  animation: scroll_effect 2.75s ease-in-out infinite;
}

</style>
