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

.form
  box-shadow: 0px 20px 50px #EAEEE9
  @apply mt-8 bg-white py-6 px-10 rounded
  &__group
    @apply mb-4 w-full
  &__label
    @apply capitalize text-sm
    color: #6A7E8A
  &__control
    @apply border-none w-full mt-1 py-1 px-1 text-dark-accent transition-colors duration-200 ease-linear
    border-bottom: 1px solid #E6E7EB
    &:focus, &:active
      @apply shadow-outline outline-none
</style>
