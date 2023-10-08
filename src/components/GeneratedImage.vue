<template>
  <div class="image-container">
    <div v-if="!loading && image">
      <img :src="image" alt="generated imgae" />
    </div>
    <div v-else>
      <h2 class="loading">Loading...</h2>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      default: ''
    },
    loading: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>
.image-container {
  width: 100%;
  padding: 0 1.5rem;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 1.35rem;
}

.image-container img {
  width: 550px;
  border: 1px solid white;
  border-radius: 10px;
}
.loading {
  color: white;
}
</style>
