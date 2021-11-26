<template>
  <main>
    <div class="card mb-4 shadow-lg border border-secondary bg-dark text-light">
      <img
        class="card-img-top"
        :src="'https://image.tmdb.org/t/p/w500/' + movie.poster_path"
        alt="Card image cap"
      />
      <div class="card-body">
        <p class="card-text">{{ movie.title }}</p>
        <div class="">
          <div class="d-flex justify-content-between align-items-center">
            <div class="btn-group">
              <button type="button" class="btn btn-sm btn-outline-secondary">
                <i class="fas fa-heart"></i>
              </button>
              <button type="button" class="btn btn-sm btn-outline-secondary">
                <i class="fas fa-plus"></i>
              </button>
            </div>
            <small class="ms-auto text-muted"
              >Rating {{ movie.vote_average }}/10</small
            >
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
<script>
export default {
  name: "MovieCard",
  props: {
    movie: {
      type: Object,
      required: true,
    },
  },
};
</script>
