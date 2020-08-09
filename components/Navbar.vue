<template>
  <nav class="navbar" :data-opened="opened">
    navbar
  </nav>
</template>

<script>
export default {
  data () {
    return {
      opened: 'false'
    }
  }
}
</script>

<style lang="sass">
  .navbar
    @apply fixed bottom-0 w-18 bg-white shadow z-30
    @apply transition-all duration-300 ease-linear
    top: 4.5rem
    left: -4.5rem
    &[data-opened=true]
      left: 0
    @screen md
      left: 0
</style>
