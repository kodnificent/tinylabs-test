<template>
  <nav class="navbar" :data-opened="opened">
    <ul class="navbar__nav">
      <li class="navbar__item">
        <a class="navbar__link" href="#">
          <dashboard-icon class="navbar__icon" opacity="0.5" />
          <span class="sr-only">dashboard</span>
        </a>
      </li>

      <li class="navbar__item">
        <a class="navbar__link" data-active href="#">
          <users-icon class="navbar__icon" opacity="0.5" />
          <span class="sr-only">employees</span>
        </a>
      </li>

      <li class="navbar__item">
        <a class="navbar__link" href="#">
          <payment-icon class="navbar__icon" opacity="0.5" />
          <span class="sr-only">my cards</span>
        </a>
      </li>
    </ul>
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
    &__nav
      @apply mt-24 flex flex-col items-center justify-center
    &__item
      @apply w-full
      &:not(:first-child)
        @apply mt-12
    &__link
      @apply flex items-center justify-center py-4 border-l-4 border-transparent transition-all
      @apply duration-300 ease-in
      &[data-active], &:hover, &:focus, &:active
        @apply border-primary
        .navbar__icon
          stroke: theme('colors.primary')
          opacity: 1
</style>
