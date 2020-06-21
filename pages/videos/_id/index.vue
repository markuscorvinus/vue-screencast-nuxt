<template>
  <div>
    We are now in video {{ video.title }}
    <nuxt-link
      :to="`/videos/${video.id}/edit`"
    >
      <button>edit</button>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/require-prop-types
  props: ['video'],
  head: {
    title: 'Watch'
  }
}
</script>

<style>

</style>
