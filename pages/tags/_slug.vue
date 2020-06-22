<template>
  <div class="posts">
    <h1>Tags: {{ $route.params.slug }}</h1>
    <PostCard v-for="post in posts" :key="post.dir" :post="post" />
  </div>
</template>
<script>
export default {
  async asyncData({ params, error, $content }) {
    try {
      const posts = await $content("posts", { deep: true })
        .where({ tags: { $contains: params.slug } })
        .fetch();
      return { posts };
    } catch (err) {
      error({
        statusCode: 404,
        message: "Page could not be found",
      });
    }
  },
  head() {
    return {
      title: "Tags",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Cool nuxt blog tags",
        },
      ],
      link: [
        {
          rel: "canonical",
          href: "https://nuxt-blog.com/tags",
        },
      ],
    };
  },
};
</script>
