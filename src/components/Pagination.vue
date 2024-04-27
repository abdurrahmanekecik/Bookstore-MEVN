<template>
  <div>
    <nav aria-label="Page navigation example">
      <ul class="pagination justify-content-end">
        <li
          class="page-item"
          :class="{ disabled: currentPage === 1 }"
          v-on:click="goToPage(currentPage - 1)"
        >
          <a class="page-link" href="#" aria-label="Previous">
            <span aria-hidden="true">&laquo;</span>
          </a>
        </li>
        <li
          :class="{ active: currentPage === page }"
          class="page-item"
          v-for="page in totalPages"
          :key="page"
        >
          <a class="page-link" v-on:click="goToPage(page)">{{ page }}</a>
        </li>

        <li
          class="page-item"
          v-on:click="goToPage(currentPage + 1)"
          :class="{ disabled: currentPage === totalPages }"
        >
          <a class="page-link" href="#" aria-label="Next">
            <span aria-hidden="true">&raquo;</span>
          </a>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'Pagination',
  emits: ['page-changed'],
  props: {
    currentPage: {
      type: Number,
      default: 1
    },
    totalPages: {
      type: Number,
      default: 1
    }
  },
  methods: {
    goToPage(page) {
      this.$emit('page-changed', page)
    }
  }
}
</script>

<style lang="scss" scoped></style>
