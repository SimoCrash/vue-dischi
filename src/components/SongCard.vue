<template>
  <div class="col">
    <div class="contents text-center">
        <img class="poster img-fluid" :src="poster" :alt="title">
        <h1 class="title"> {{ title }}</h1>
        <div class="details">
            <div class="author">{{ author }}</div>
            <div class="year">{{ year }}</div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'SongCard',
    props: {
        poster: String,
        title: String,
        author: String,
        year: String,
        selectedValue: String,
    }

}
</script>

<style lang="scss" scoped>
  .col {
    
    .contents {
      padding: 1rem;
      background-color: #2E3A46;
      height: 100%;
      .title {
        color:white;
        text-transform: uppercase;
      }
      .details {
        color: #81807B;
      }
    }
  }
</style>