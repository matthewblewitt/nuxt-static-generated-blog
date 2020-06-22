<template>
  <div class="posts">
    <h1>Posts</h1>
    <PostCard v-for="post in posts" :key="post.dir" :post="post" />
  </div>
</template>
<script>
import PostCard from "~/components/PostCard";
export default {
  components: {
    PostCard,
  },
  async asyncData({ params, error, $content }) {
    try {
      const posts = await $content("posts", { deep: true }).fetch();
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
      title: "Nuxt blog",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Cool nuxt blog",
        },
      ],
      link: [
        {
          rel: "canonical",
          href: "https://nuxt-blog.com/",
        },
      ],
    };
  },
};
</script>
