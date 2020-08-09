<template>
  <table class="data-table">
    <thead>
      <tr>
        <th>
          <button class="checkbox">
            <span class="sr-only">select all</span>
          </button>
        </th>
        <th>first name</th>
        <th>last name</th>
        <th>email</th>
        <th>phone</th>
        <th>role</th>
        <th>
          <span class="sr-only">actions</span>
        </th>
      </tr>
    </thead>

    <tbody>
      <tr v-for="item in items" :key="item.id">
        <td>
          <button class="checkbox">
            <span class="sr-only">select item</span>
          </button>
        </td>
        <td><span class="data-text">{{ item.first_name }}</span></td>
        <td><span class="data-text">{{ item.last_name }}</span></td>
        <td><span class="data-text">{{ item.email }}</span></td>
        <td><span class="data-text">{{ item.phone }}</span></td>
        <td><span class="data-text">{{ item.role }}</span></td>
        <!-- actions -->
        <td>
          <button>
            <trash-icon />
            <span class="sr-only">delete item</span>
          </button>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: {
    items: { type: Array, required: true }
  }
}
</script>

<style lang="sass">
  .data-table
    width: 100%
    border-collapse: separate
    border-spacing: 0 1rem
    th
      font-size: 14px
      line-height: 15px
      padding: 0 1rem
      @apply text-dark-accent font-normal uppercase
    th, td
      text-align: left
      vertical-align: middle
    tbody
      td
        padding: 0.75rem 1rem
        @apply bg-white
        &:first-child
          @apply rounded-tl-md rounded-bl-md
        &:last-child
          @apply rounded-tr-md rounded-br-md
        .data-text
          color: #6A7E8A
          font-size: 16px

  .checkbox
    width: 12px
    height: 12px
    border: 1.2px solid rgba(106, 126, 138, 0.4)
    border-radius: 0.5px
    &[data-checked]
      @apply bg-primary
</style>
