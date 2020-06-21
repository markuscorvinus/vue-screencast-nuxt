<template>
  <div>
    <h1>Videos</h1>
    <div
      v-for="video in $store.state.videos"
      :key="video.id"
    >
      <nuxt-link
        :to="`/videos/${ video.id }`"
      >
        {{ video.title }}
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  async fetch ({ $axios, store }) {
    const response = await $axios.get('/posts')
    const videos = response.data

    store.commit('SET_VIDEOS', videos)
  },
  head: {
    title: 'Vue Screencast - Videos'
  }
}
</script>

<style>

</style>
