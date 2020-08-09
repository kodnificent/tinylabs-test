<template>
  <div>
    <Nuxt />
  </div>
</template>

<style lang="sass">
html
  @apply text-gray-800 antialiased leading-normal

h1, h2, h3, h4, h5, h6, p
  @apply text-dark-accent

h1, h2, h3, h4, h5, h6
  @apply leading-tight font-medium

h1
  @apply text-2xl

h2
  @apply text-xl

h3
  @apply text-lg

a
  @apply text-primary no-underline outline-none
  &:focus
    @apply outline-none

button
  @apply outline-none
  &:focus
    @apply outline-none
  &:disabled,
  &[disabled],
  &.disabled
    @apply opacity-50 cursor-not-allowed

.btn
  border-radius: 3px
  text-transform: capitalize
  font-size: 16px
  min-height: 44px
  @apply font-medium
  &:focus, &:active
    @apply outline-none shadow-outline
  &--lg
    @apply text-lg
  &--sm
    min-height: 34px
    @apply text-sm
  &--with-shadow
    box-shadow: 0px 7px 15px rgba(43, 218, 83, 0.2)
</style>
