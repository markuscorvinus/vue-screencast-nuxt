<template>
  <div>
    You are now editing {{ video.title }}
    <nuxt-link
      :to="`/videos/${video.id}`"
    >
      <button>return</button>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/require-prop-types
  props: ['video'],
  head: {
    title: 'Edit'
  }
}
</script>

<style>

</style>
