<template>
  <div class="post">
    <v-img class="img" :src="post.image" alt="Cat"></v-img>
    <div>
      <h3 class="heading">{{ post.title }}</h3>
      <p>{{ post.description }}</p>
      <v-tags :tags="post.tags" />
      <nuxt-link :to="post.dir">Read more</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.post {
  border-radius: 8px;
  box-shadow: 1px 1px 10px 0 rgba(32, 33, 36, 0.1);
  padding: 15px 20px;
  margin: 10px 0;
  display: flex;
}
.img {
  width: 200px;
  min-width: 200px;
  margin-right: 10px;
  padding: 0;
  position: relative;
}
.img /deep/ img {
  position: absolute;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.heading {
  margin-bottom: 5px;
}
</style>
