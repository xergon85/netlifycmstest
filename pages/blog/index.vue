<template>
  <ul>
    <li v-for="post of posts" :key="post.slug">
      <NuxtLink
        :to="{
          name: 'blog-slug', params: { slug: post.slug}
        }"
      >
        {{ post.title }}
      </NuxtLink>
    </li>
  </ul>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const posts = await $content('blog').fetch()

    return {
      posts
    }
  }
}
</script>
