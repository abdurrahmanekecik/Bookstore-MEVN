<template>
  <section>
    <div class="container">
      <SectionHeader :title="sectionTitle" :text="sectionText" />
      <button>Back</button>
      <div class="row mb-4">
        <div class="col-lg-6">
          <img class="card-img-top" src="/public/assets/images/b1.jpg" />
        </div>
        <div class="col-lg-6">
          <h4 class="lead description">{{ book.name }}</h4>
          <p class="lead description">{{ book.description }}</p>
          <div class="mb-4">
            <div class="row border-bottom pb-2">
              <div class="col-lg-6">
                <strong>Page</strong>
              </div>
              <div class="col-lg-6">
                <span>{{ book.page }}</span>
              </div>
            </div>
            <div class="row border-bottom pb-2">
              <div class="col-lg-6">
                <strong>Author</strong>
              </div>
              <div class="col-lg-6">
                <span>{{ book.author }}</span>
              </div>
            </div>
            <div class="row border-bottom pb-2">
              <div class="col-lg-6">
                <strong>Rating</strong>
              </div>
              <div class="col-lg-6">
                <span>{{ book.rating }}</span>
              </div>
            </div>
            <div class="row border-bottom pb-2">
              <div class="col-lg-6">
                <strong>Upload Date</strong>
              </div>
              <div class="col-lg-6">
                <span>{{ book.uploadDate }}</span>
              </div>
            </div>

            <div class="comments-section">
              <h3 class="display-6 mb-2">Comments</h3>
              <div class="card mb-2">
                <div class="card-body">
                  <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas, reprehenderit.
                  </p>
                  <div class="d-flex justify-content-between">
                    <p class="fw-bold fst-italic">John Doe</p>
                    <div class="d-flex align-items-center">
                      <p>Upvote</p>
                      <p class="ps-2"><strong>8</strong></p>
                    </div>
                  </div>
                </div>
              </div>
              <div class="card mb-2">
                <div class="card-body">
                  <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas, reprehenderit.
                  </p>
                  <div class="d-flex justify-content-between">
                    <p class="fw-bold fst-italic">John Doe</p>
                    <div class="d-flex align-items-center">
                      <p>Upvote</p>
                      <p class="ps-2"><strong>8</strong></p>
                    </div>
                  </div>
                </div>
              </div>
              <div class="card mb-2">
                <div class="card-body">
                  <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas, reprehenderit.
                  </p>
                  <div class="d-flex justify-content-between">
                    <p class="fw-bold fst-italic">John Doe</p>
                    <div class="d-flex align-items-center">
                      <p>Upvote</p>
                      <p class="ps-2"><strong>8</strong></p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import SectionHeader from '@/components/SectionHeader.vue'
import fakeData from '@/fakeData.js'
export default {
  name: 'BookDetailVie',
  data() {
    return {
      sectionTitle: 'Book Detail',
      sectionText: 'Book Detail Text'
    }
  },
  components: {
    SectionHeader
  },
  created() {
    const bookId = this.$route.params.id
    this.book = fakeData.find((book) => book.id === parseInt(bookId))
  }
}
</script>

<style scoped>
.details-wrapper {
  max-height: 740px;
  display: flex;
  flex-direction: column;
}
.comments-section {
  flex-grow: 1;
  overflow-y: auto;
}
.description {
  min-height: 150px;
  max-height: 250px;
  overflow-y: auto;
}
</style>
