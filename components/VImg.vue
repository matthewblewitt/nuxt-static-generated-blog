<template>
  <div class="img">
    <img :src="imgSrc()" :alt="alt" />
  </div>
</template>

<script>
export default {
  props: {
    src: {
      type: String,
      required: true,
    },
    alt: {
      type: String,
      required: true,
    },
  },
  methods: {
    imgSrc() {
      try {
        const { post } = this.$parent;
        return require(`~/content${post.dir}/img/${this.src}`);
      } catch (error) {
        return null;
      }
    },
  },
};
</script>

<style scoped>
.img {
  border: 1px solid #eee;
  border-radius: 5px;
  padding: 5px;
}
img {
  max-width: 100%;
  width: 100%;
  object-fit: cover;
}
</style>
