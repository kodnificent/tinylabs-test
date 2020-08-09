<template>
  <div class="bg-gray-100 xl:bg-white flex min-h-screen">
    <div class="hidden xl:block relative xl:w-2/5 image-container">
      <div
        class="image-container__content absolute left-0 top-0 h-full w-full flex flex-col pb-16 px-20
        items-center justify-end"
      >
        <p class="text-center text-white text-xl font-medium">
          No Hazzles
        </p>

        <p class="mt-5 text-xl px-4 text-center text-white">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod.
        </p>

        <div class="slide mt-8">
          <button class="slide__button" data-current="true" aria-current="true">
            <span class="sr-only">slide 1</span>
          </button>

          <button class="slide__button">
            <span class="sr-only">slide 2</span>
          </button>
        </div>
      </div>
    </div>

    <div
      class="pt-16 md:pt-24 pb-8 w-full px-4 md:px-8 xl:px-12
      flex flex-col justify-between xl:w-3/5"
    >
      <!-- signup form-->
      <div class="xl:w-3/5 mx-auto">
        <div class="text-center xl:text-left">
          <h1 class="text-xl md:text-2xl xl:text-3xl">
            Create your free account
          </h1>

          <p class="mt-2">
            Already registered? <a href="#">Sign in</a>
          </p>
        </div>

        <form class="form" @submit.prevent="submitForm">
          <div class="form-group flex flex-wrap">
            <div class="w-full xl:w-1/2 xl:pr-5 mb-4 xl:mb-0">
              <label class="form-label">first name</label>
              <input type="text" class="form-control" value="Jane">
            </div>

            <div class="w-full xl:w-1/2 xl:pl-5">
              <label class="form-label">last name</label>
              <input type="text" class="form-control" value="Clement">
            </div>
          </div>

          <div class="form-group">
            <label class="form-label">email</label>
            <input type="email" class="form-control" value="jane.clement@gmail.com">
          </div>

          <div class="form-group">
            <label class="form-label">password</label>
            <input type="password" class="form-control" value="**********">
          </div>

          <div class="mt-12 flex justify-center md:justify-end">
            <button class="btn btn--lg btn--with-shadow bg-primary text-white w-full md:w-48">
              continue
            </button>
          </div>
        </form>
      </div>

      <!-- copyright -->
      <div class="flex flex-wrap mt-8">
        <div class="w-full md:w-1/2 mb-1 xl:mb-0">
          <p class="text-xs text-center md:text-left text-gray-600">
            By signing up, you agree to our <a href="#">Terms</a> and <a href="#">Privacy Policy</a>
          </p>
        </div>

        <div class="w-full md:w-1/2">
          <p class="text-xs text-center md:text-right text-gray-600">
            &copy; 2019 Tinylabs. All rights reserved.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    submitForm () {
      // redirect to home page
    }
  }
}
</script>

<style lang="sass" scoped>
  .image-container
    background-image: url('/signup.jpg')
    &__content
      background: linear-gradient(180deg, rgba(57, 54, 54, 0.0001) 47.22%, rgba(0, 0, 0, 0.554688) 86.26%)
      @apply text-white

  .slide
    &__button
      width: 10px
      height: 10px
      background: #D0E8DF
      border-radius: 5.25px
      &[data-current=true]
        @apply bg-primary
        &::after
          content: ''
          display: block
          width: 18px
          height: 18px
          margin: -4px 0 0 -4px
          border-radius: 9999px
          border: 1px solid white
      &:not(:first-child)
        margin-left: 0.5rem
      &--current

  .form
    box-shadow: 0px 20px 50px #EAEEE9
    @apply mt-8 bg-white py-6 px-10 rounded
    .form-group
      @apply mb-4 w-full
      .form-label
        @apply capitalize text-sm
        color: #6A7E8A
      .form-control
        @apply border-none w-full mt-1 py-1 px-1 text-dark-accent transition-colors duration-200 ease-linear
        border-bottom: 1px solid #E6E7EB
        &:focus, &:active
          @apply shadow-outline outline-none
</style>
