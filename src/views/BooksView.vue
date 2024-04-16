<template>
  <section>
    <div class="container">
      <SectionHeader :title="sectionTitle" :text="sectionText" />
      <BookList :books="books" />
      totalPages: {{ totalPages }}
      <Pagination :currentPage="currentPage" :totalPages="totalPages" />
    </div>
  </section>
</template>

<script>
import SectionHeader from '@/components/SectionHeader.vue'
import BookList from '@/components/BookList.vue'
import books from '@/fakeData.js'
import Pagination from '@/components/Pagination.vue'
export default {
  name: 'BooksView',
  components: {
    SectionHeader,
    BookList,
    Pagination
  },
  data() {
    return {
      books: books,
      sectionTitle: 'Books',
      sectionText: 'Books Text',
      currentPage: 1,
      itemsPerPage: 3
    }
  },
  computed: {
    totalPages() {
      return Math.ceil(this.books.length / this.itemsPerPage)
    },
    paginatedBooks() {
      const start = (this.currentPage - 1) * this.itemsPerPage
      const end = start + this.itemsPerPage
      return this.books.slice(start, end)
    }
  }
}
</script>

<style scoped>
.auth-box {
  margin-top: -30px;
}
</style>
