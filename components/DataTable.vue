<template>
  <table class="data-table">
    <thead>
      <tr>
        <th>
          <button class="checkbox" :data-checked="allItemsAreChecked" @click.prevent="toggleCheckAllItems()">
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
          <button class="checkbox" :data-checked="item.is_checked" @click.prevent="toggleItemCheck(item)">
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
          <button @click.prevent="deleteItem(item)">
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
  data () {
    return {
      endpoint_uri: 'https://crudcrud.com/api/67d87f85f807443ea1ad1f0718fbb0c0/',
      items: [
        {
          id: 1,
          first_name: 'Victor',
          last_name: 'Mbamara',
          email: 'victor@example.com',
          phone: '08153035817',
          role: 'Admin'
        },
        {
          id: 2,
          first_name: 'Joshua',
          last_name: 'Bakare',
          email: 'victor@example.com',
          phone: '08153035817',
          role: 'Admin'
        },
        {
          id: 3,
          first_name: 'Jane',
          last_name: 'Doe',
          email: 'victor@example.com',
          phone: '08153035817',
          role: 'Admin'
        },
        {
          id: 4,
          first_name: 'David',
          last_name: 'Isong',
          email: 'victor@example.com',
          phone: '08153035817',
          role: 'Admin'
        },
        {
          id: 5,
          first_name: 'Mark',
          last_name: 'Zuckerberg',
          email: 'victor@example.com',
          phone: '08153035817',
          role: 'Admin'
        }
      ]
    }
  },

  computed: {
    allItemsAreChecked () {
      const checkedItems = this.items.filter((item) => {
        return item.is_checked === true
      })

      return checkedItems.length === this.items.length
    }
  },

  mounted () {
    this.items.forEach((item) => {
      this.$set(item, 'is_checked', false)
    })
  },

  methods: {
    deleteItem (item) {
      // first we make our api call to delete the item from the server
      // make api call here

      // next we delete the item from our array
      const index = this.items.indexOf(item)
      this.items.splice(index, 1)
    },

    getItems () {
      fetch(this.endpoint_uri + 'employees').then((res) => {
        this.items = res.data
        // eslint-disable-next-line
      }).catch((err) => {
        // we display errors if any
      }).finally(() => {
        // we stop our loading button
      })
    },

    toggleItemCheck (item) {
      if (item.is_checked) {
        item.is_checked = false
      } else {
        item.is_checked = true
      }
    },

    toggleCheckAllItems () {
      if (this.allItemsAreChecked) {
        this.checkAllItems()
      } else {
        this.uncheckAllItems()
      }
    },

    checkAllItems () {
      this.items.forEach((item) => {
        item.is_checked = true
      })
    },

    uncheckAllItems () {
      this.items.forEach((item) => {
        item.is_checked = false
      })
    }
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
