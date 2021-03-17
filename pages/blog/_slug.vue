<template>
  <div>
    <h1>{{ article.title }}</h1>
    <p>{{ article.description }}</p>
    <span>====</span>
    <nuxt-content :document="article" />
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params, error }) {
    const article = await $content('articles', params.slug)
      .fetch()

    return {
      article
    }
  }
}
</script>
