<template>
  <section>
    <div class="container">
      <SectionHeader :title="sectionTitle" :text="sectionText" />
      <BookList :books="books" />
    </div>
  </section>
</template>

<script>
import SectionHeader from '@/components/SectionHeader.vue'
import BookList from '@/components/BookList.vue'
import books from '@/fakeData.js'
export default {
  name: 'BooksView',
  components: {
    SectionHeader,
    BookList
  },
  data() {
    return {
      books: books,
      sectionTitle: 'Books',
      sectionText: 'Books Text'
    }
  }
}
</script>

<style scoped>
.auth-box {
  margin-top: -30px;
}
</style>
