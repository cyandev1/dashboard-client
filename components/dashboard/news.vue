<template>
  <div class="flex flex-col border-yellow-400 border-2 rounded">
    <h1 class="text-2xl font-medium bg-yellow-400 border text-center w-full pt-2 pb-1">
      <nuxt-link to="/news">
        {{ title }}
      </nuxt-link>
    </h1>
    <div class="content_wrapper pt-3 flex flex-col items-center">
      <h1 class="text-2xl font-medium ml-10 text-center">
        {{ headline }}
      </h1>
      <span class="mt-1 mx-8">
        {{ contentSnippet }}
      </span>
    </div>
  </div>
</template>

<script>
import store from '../../store'

export default {
  data () {
    return {
      title: 'News'
    }
  },
  computed: {
    headline () {
      return store.news.title.substring(0, 50)
    },
    contentSnippet () {
      return store.news.contentSnippet
    }
  }
}
</script>

<style lang="scss" scoped>
.content_wrapper {
  background-color: #C8D7F1;
  opacity: 0.7;
  height: 100%;
}
</style>
