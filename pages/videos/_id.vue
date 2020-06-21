<template>
  <nuxt-child :video="video" />
</template>

<script>
import { mapState } from 'Vuex'

export default {
  async fetch ({ $axios, params, store }) {
    const response = await $axios.get(`/posts/${params.id}`)
    const video = response.data

    store.commit('SET_CURRENT_VIDEO', video)
  },
  computed: {
    ...mapState({
      video: 'currentVideo'
    })
  },
  head () {
    return {
      titleTemplate: `%s - ${this.video.title}`
    }
  }

}
</script>

<style>

</style>
