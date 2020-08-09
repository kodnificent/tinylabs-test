<template>
  <div class="bg-gray-100 min-h-screen">
    <div class="w-full">
      <topbar />
      <navbar />
    </div>

    <main class="md:ml-18 py-8 md:py-16 lg:py-20 px-4 md:px-10 lg:px-18 mt-18">
      <div class="flex">
        <div>
          <h1>Employees</h1>
        </div>

        <!-- eslint-disable-next-line -->
        <div class="flex-grow"></div>

        <div>
          <button class="btn btn--with-shadow bg-primary text-white md:w-48 w-32">
            add new
          </button>
        </div>
      </div>

      <div class="flex flex-col md:flex-row md:items-center mt-10 py-8 px-6 bg-white rounded-md">
        <h1 class="capitalize lg:text-4xl">
          josh bakery ventures
        </h1>

        <!-- eslint-disable-next-line -->
        <div class="flex-grow"></div>

        <p class="capitalize lg:text-xl">
          62, bode thomas surulere, lagos.
        </p>
      </div>

      <!-- action area -->
      <div class="flex flex-wrap items-center mt-9">
        <form @submit.prevent>
          <label class="sr-only">
            Change role of selected users
          </label>

          <select class="custom-select">
            <option disabled selected>
              Change role
            </option>

            <option value="admin">
              Admin
            </option>

            <option value="staff">
              Staff
            </option>
          </select>

          <button class="ml-3 btn btn--sm bg-primary text-white w-24">
            change
          </button>
        </form>

        <!-- eslint-disable-next-line -->
        <form class="search-form" @submit.prevent>
          <label class="search-label">
            <search-icon />
            <span class="sr-only">search employee</span>
          </label>

          <input placeholder="Enter staff name here..." class="search-input" type="search">
        </form>
      </div> <!-- /action area ends -->

      <div class="mt-8 overflow-x-auto">
        <data-table />
      </div>
    </main>
  </div>
</template>

<style lang="sass">
  .custom-select
    display: inline-block
    appearance: none
    background-color: white
    font-size: 14px
    padding: 0.5rem 1.5rem .5rem .75rem
    border: 1px solid rgba(106, 126, 138, 0.4)
    border-radius: 3px
    color: #6A7E8A
    background-image: url("data:image/svg+xml,%3Csvg width='10' height='6' viewBox='0 0 10 6' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M9 5L5 1L1 5' stroke='%236A7E8A' stroke-width='1.2' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/svg%3E%0A"),
    url("data:image/svg+xml,%3Csvg width='10' height='6' viewBox='0 0 10 6' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M1 1L5 5L9 1' stroke='%236A7E8A' stroke-width='1.2' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/svg%3E%0A")
    background-repeat: no-repeat, no-repeat
    background-position: right .7em top 40%, right .7em top 60%
    background-size: .65em auto, .65em auto
    &::-ms-expand
      display: none
    &:focus, &:active
      @apply outline-none shadow-outline
      option[disabled]
        @apply text-gray-500

  .search-form
    @apply relative mt-4 w-full
    @screen md
      width: 300px
      @apply ml-4 mt-0

  .search-input
    border: 1px solid rgba(106, 126, 138, 0.4)
    border-radius: 3px
    padding-top: .35rem
    padding-bottom: .35rem
    @apply pl-2 pr-4 w-full
    &:focus, &:active
      @apply outline-none shadow-outline

  .search-label
    @apply absolute right-0 flex items-center px-2 h-full
</style>
