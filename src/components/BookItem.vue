<template>
  <div class="card border-0 shadow position-relative">
    <img src="../../public/assets/images/b1.jpg" alt="" class="card-img-top" />
    <div class="card-body">
      <div class="auth-box text-center">
        <span style="background-color: #063547" class="py-1 px-3 text-white rounded-pill">{{
          book.author
        }}</span>

        <h5 class="card-title mt-3 fw-semibold">{{ book.name }}</h5>
        <p class="card-text">
          {{ book.description }}
        </p>
        <div class="mb-1 d-flex justify-content-between align-items-center">
          <a href="#" class="card-link">Read More</a>
          <p style="background-color: #063547" class="py-1 px-2 text-white badge mb-0">
            {{ book.uploadDate }}
          </p>
        </div>
      </div>
      <span
        :class="ratingBadgeClass"
        class="position-absolute top-0 bg-info start-100 translate-middle p-2 bg-info text-light rounded-circle border border-2 border-light"
      >
        {{ book.rating }}
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BookItem',
  props: {
    book: {
      type: Object,
      default: () => {}
    }
  },
  computed: {
    ratingBadgeClass() {
      if (this.book.rating > 7) {
        return 'bg-success'
      } else if (this.book.rating > 5) {
        return 'bg-warning'
      } else {
        return 'bg-danger'
      }
    }
  }
}
</script>

<style lang="scss" scoped></style>
