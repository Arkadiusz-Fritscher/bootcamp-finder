<template>
  <div>
    <h1>Content</h1>
    <div>
      <div v-for="bootcamp in bootcamps" :key="bootcamp.slug">
        {{ bootcamp.title }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const bootcamps = await $content('bootcamps').fetch()

    return {
      bootcamps,
    }
  },
}
</script>

<style scoped></style>
