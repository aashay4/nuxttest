<template lang="html">
  <div class="w3-row">
  <nuxt-link
  :to="id">
    <article>
      <div
      :style="{backgroundImage: 'url(' + thumbnailImage + ')'}"
      class="post-preview-thumbnail"></div>
      <div>
        <h3>{{ title }}</h3>
        <p>{{ excert }}</p>
      </div>
    </article>
  </nuxt-link>
</div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    excert: {
      type: String,
      required: true
    },
    thumbnailImage: {
      type: String,
      required: true
    },
    id: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
a {
  text-decoration: none;
  color: black;
}

.post-preview {
  border-radius: 3px;
  box-shadow: 1px 1px 5px 1px rgba(0, 0 ,0, 0.5);
  width: 90%;
  height: 20rem;
  margin-left: 1rem;
}

.post-preview-thumbnail {
  background-position: center;
  background-size: cover;
  width: 100%;
  height: 15rem;
}

.post-preview-content {
  text-align: center;
  padding: 1rem;
}

@media (min-width: 35rem) {
  .post-preview {
    width: 25rem;
    margin: 1rem;
  }
}
</style>
